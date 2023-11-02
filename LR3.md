# 1. Part 1 - Bugs
(1) A failure-inducing input for the buggy program:
```
@Test 
public void testReverseInPlace1() {
  int[] input1 = { 3, 5, 7, 9, 11 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 11, 9, 7, 5, 3 }, input1);
}
```
(2) An input that doesn’t induce a failure:
```
@Test 
public void testReverseInPlace2() {
  int[] input1 = { 3 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 3 }, input1);
}
```
(3) The symptom, as the output of running the tests:
![Image](test.png) <br>
(4) The buggy code:
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {     
    arr[i] = arr[arr.length - i - 1];
  }    
}
```
The fixed code:
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length/2; i += 1) {  
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}
```
# 2. Part 2 - Researching Commands
(1) grep -c: displays the count of matching lines instead of the actual lines (resource: https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
```
AD+yid008@DESKTOP-LQADC83 MINGW64 ~/Documents/GitHub/docsearch/technical/911report (main)
$ grep -c "flight" *.txt
chapter-1.txt:74
chapter-10.txt:10
chapter-11.txt:7
chapter-12.txt:5
chapter-13.1.txt:0
chapter-13.2.txt:39
chapter-13.3.txt:9
chapter-13.4.txt:28
chapter-13.5.txt:50
chapter-2.txt:1
chapter-3.txt:14
chapter-5.txt:27
chapter-6.txt:15
chapter-7.txt:59
chapter-8.txt:8
chapter-9.txt:3
preface.txt:0
```
This command line prints a count of lines in each file in the folder 911 report that contains the word "flight". We can see most of the files contain many lines with the word "flight", which is consistent with the topic -- 911report. In this way, we can know the main thing that happened in 911 was about the flight.
```
AD+yid008@DESKTOP-LQADC83 MINGW64 ~/Documents/GitHub/docsearch/technical/government/About_LSC (main)
$ grep -c "gender" *.txt
Comments_on_semiannual.txt:1
commission_report.txt:0
conference_highlights.txt:0
CONFIG_STANDARDS.txt:1
diversity_priorities.txt:5
LegalServCorp_v_VelazquezDissent.txt:0
LegalServCorp_v_VelazquezOpinion.txt:0
LegalServCorp_v_VelazquezSyllabus.txt:0
ODonnell_et_al_v_LSCdecision.txt:0
ONTARIO_LEGAL_AID_SERIES.txt:0
Progress_report.txt:2
Protocol_Regarding_Access.txt:0
reporting_system.txt:0
Special_report_to_congress.txt:0
State_Planning_Report.txt:0
State_Planning_Special_Report.txt:0
Strategic_report.txt:2
```
This command line prints a count of lines in each file in the folder government/About_LSC that contains the word "gender". By using this command, we can know which file is talking about the gender topic and which file considers more about the gender topic.<br>
(2) grep -n: displays line numbers along with the matching lines (resource: https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
```
AD+yid008@DESKTOP-LQADC83 MINGW64 ~/Documents/GitHub/docsearch/technical/government/About_LSC (main)
$ grep -n "gender" diversity_priorities.txt
19:age, gender, disability, sexual orientation, race, ethnicity and
138:greater gender diversity and pursued activities to bring women into
160:transgendered persons, persons with AIDS, children, homeless
170:transgendered persons, people of color, people from diverse
418:religious groups and gays/lesbians/bi-sexual and transgender
```
Since this command displays the lines containing "gender" and their line numbers, it makes it easier for us to locate which part is talking about the gender topic in the file.
AD+yid008@DESKTOP-LQADC83 MINGW64 ~/Documents/GitHub/docsearch/technical/911report (main)
```
$ grep -n "kill" chapter-2.txt
19:            He claimed it was more important for Muslims to kill Americans than to kill other
20:                infidels." It is far better for anyone to kill a single American soldier than to
36:            Though novel for its open endorsement of indiscriminate killing, Bin Ladin's 1998
43:                Kingdom. It praised the 1983 suicide bombing in Beirut that killed 241 U.S. Marines,
64:                historical moment. How did Bin Ladin-with his call for the indiscriminate killing of
214:                especially clear in Egypt. Confronted with a violent Islamist movement that killed
259:                enormous number trained only in religious schools, lacked the skills needed by their
260:                societies. Far more acquired valuable skills but lived in stagnant economies that
266:                abroad, lacked the perspective and skills needed to understand a different culture.
312:                appeared to be ungainly but was in fact quite athletic, skilled as a horseman,
365:                November 24, 1989, when a remotely controlled car bomb killed Azzam and both of his
366:                sons. The killers were assumed to be rival Egyptians. The outcome left Bin Ladin
507:                where U.S. troops routinely stopped en route to Somalia, killing two, but no
524:                were killed. The Saudi government arrested four perpetrators, who admitted being
533:                Americans were killed, and 372 were wounded. The operation was carried out
543:            Another scheme revealed that Bin Ladin sought the capability to kill on a mass scale.
553:                One of the al Qaeda representatives explained his mission: "it's easy to kill more
573:                killed 241 U.S. Marines in Lebanon in 1983. The relationship between al Qaeda and
613:                1995 appears to have been a tipping point. The would-be killers, who came from the
657:                ambitions and organizational skills. He returned to Afghanistan.
687:                men with no marketable skills but with deeply held Islamic views.
935:            The attack on the U.S. embassy in Nairobi destroyed the embassy and killed 12
937:                attack on the U.S. embassy in Dar es Salaam killed 11 more people, none of them
940:                without assaulting them, even if this involved the killing of Muslims, this is
```
Since this command displays the lines containing "kill" and their line numbers, it makes it easier for us to locate which part is talking about the number of casualties on 9/11. <br>
(3) grep -w: displays lines with whole words that match the specified pattern (resource: https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
```
AD+yid008@DESKTOP-LQADC83 MINGW64 ~/Documents/GitHub/docsearch/technical/biomed (main)
$ grep -w "intersection" *.txt
1471-2105-1-1.txt:          The intersection of the nullspace and the region
1471-2105-3-34.txt:        microarrays), but when looking at the intersection of the
1471-2105-3-34.txt:        intersection of two enormous sets of functional
1471-213X-1-6.txt:          pole. The intersection of the white and gray regions
1471-2156-4-10.txt:        single marker analysis and used to define an intersection
1471-2156-4-10.txt:        intersection and the two marker test under the stated
1471-2156-4-10.txt:          difference in statistical power between the intersection
1471-2156-4-10.txt:          the intersection test for each of the parameter
1471-2156-4-10.txt:          statistical power between the intersection test and the
1471-2156-4-10.txt:          was exactly zero), 39 favoring the intersection test, and
1471-2156-4-10.txt:          27 favoring the two marker test. The intersection test
1471-2156-4-10.txt:          combinations indicated the intersection test as more
1471-2156-4-10.txt:          intersection and two marker was zero was rejected for
1471-2156-4-10.txt:          the intersection test has slightly higher power than the
1471-2156-4-10.txt:          intersection test. Results similar to those found in the
1471-2156-4-10.txt:          initial simulations indicate that the intersection test
1471-2156-4-10.txt:          scenarios favored the intersection test, while 29
1471-2156-4-10.txt:          powerful than the intersection test. However, when the
1471-2156-4-10.txt:          the intersection test is more powerful. Although we can
1471-2156-4-10.txt:          found to be significant using both the intersection test
1471-2156-4-10.txt:          non-significant with both tests. The intersection and two
1471-2156-4-10.txt:          intersection test, the two marker test, and the interval
1471-2156-4-10.txt:          intersection test showed borderline significance for one
1471-2156-4-10.txt:          35B-46C while intersection tests
1471-2156-4-10.txt:          96F-100A while the intersection
1471-2156-4-10.txt:          mapping agrees with the intersection test for interval
1471-2156-4-10.txt:          The application of the intersection test to these data
1471-2156-4-10.txt:          intersection test (see Figure 2). The regions identified
1471-2156-4-10.txt:        The application of an intersection test uses information
1471-2156-4-10.txt:        the two marker test. The use of the intersection test takes
1471-2156-4-10.txt:        theory, and typically seen in the use of union/intersection
1471-2156-4-10.txt:        intersection test is simple to implement, the expansion to
1471-2156-4-10.txt:        unlinked, the intersection test is simply the single marker
1471-2156-4-10.txt:        this case, the application of the intersection test will
1471-2156-4-10.txt:        where the power of the intersection test is equal to or
1471-2156-4-10.txt:        marker test has higher power than the intersection test. A
1471-2156-4-10.txt:        QTL than the other marker, in this case the intersection
1471-2156-4-10.txt:        tests that were not identified using the intersection test.
1471-2156-4-10.txt:        the intersection tests were small but did not exceed the
1471-2156-4-10.txt:        intersection tests, but were not significant using the two
1471-2156-4-10.txt:        region than the intersection test, while in others the
1471-2156-4-10.txt:        intersection and multiple marker approaches, or s/he may
1471-2156-4-10.txt:        with an intersection test and a multiple marker analysis
1471-2156-4-10.txt:        We find that the intersection test has equal or greater
1471-2156-4-10.txt:        intersection test. When markers are linked, as in many of
1471-2156-4-10.txt:        the intersection test is used in conjunction with a more
1471-2156-4-10.txt:        appropriate correction, the performance of the intersection
1471-2156-4-10.txt:        intersection tests versus two marker tests is to make clear
1471-2156-4-10.txt:        intersection tests are indeed equal to and/or more powerful
1471-2156-4-10.txt:          2 , hence the term intersection test.
1471-2156-4-10.txt:          conservative for the intersection test and the lack of
1471-2156-4-10.txt:          difficult for the intersection test to reject.
1471-2156-4-10.txt:          intersection test, is the simplicity of calculation of
1471-2156-4-10.txt:          For the intersection test, the null hypothesis was
1471-2156-4-10.txt:          To compare the intersection test to the two marker
1471-2156-4-10.txt:          intersection test was conducted. For the 71 unique pairs
1471-2156-4-10.txt:          of markers, concordance between the intersection test and
1471-2164-3-19.txt:        intersection in figure 2) in terms of specificity (Sp) and
1471-2164-3-19.txt:        plotted as a function of the thresholds, the intersection
gb-2002-3-11-research0062.txt:          intersection of differentially expressed genes on all
gb-2002-3-11-research0065.txt:          intersection of a constant cutoff ratio with a
gb-2002-3-12-research0081.txt:          intersection of each individual sequence alignment with
gb-2002-3-12-research0081.txt:        intersection of cDNA alignments and exons. A cDNA was
gb-2002-3-12-research0083.txt:            the re-annotation was determined using an intersection
gb-2002-3-12-research0088.txt:          genes. A black dash at the intersection of a row and a
gb-2002-3-12-research0088.txt:          intersection in the matrix was 1; otherwise it was 0. The
gb-2002-3-4-research0018.txt:        considering the intersection (or union) of genes predicted
gb-2002-3-9-research0044.txt:        overlaps. Why is such little intersection observed between
gb-2002-3-9-research0044.txt:        consequently to the relatively limited intersection between
gb-2003-4-2-r9.txt:          generate four independent output sets. The intersection
gb-2003-4-2-r9.txt:          the first intersection, the self-binding and complexity
gb-2003-4-2-r9.txt:          filters are incrementally relaxed until an intersection
```
This command ensures that we only get lines that have the whole word "intersection" but not just the word "intersect" or something else in the files in biomed folder.
```
AD+yid008@DESKTOP-LQADC83 MINGW64 ~/Documents/GitHub/docsearch/technical/plos (main)
$ grep -w "overwhelming" *.txt
journal.pbio.0020001.txt:        several scientists, who present overwhelming evidence for the disparity in scientific
journal.pbio.0020001.txt:        ecology and environmental sciences emphasizes the overwhelming contributions of authors
journal.pbio.0020013.txt:        subject to multiple levels of regulation. In the overwhelming majority of cases, selected
journal.pbio.0020042.txt:        also reinforces the notion that the overwhelming value of bioinformatics is to generate
journal.pbio.0020172.txt:        either finding the overwhelming hold to pin down the other. More than one hundred twenty
journal.pbio.0020241.txt:        and reliability. Consequently, this strain combination is at the origin of the overwhelming
pmed.0010010.txt:        therapy into such a remote area are overwhelming—and some may question whether this is a
pmed.0020016.txt:        Africa, where the overwhelming majority of people living with and dying from HIV/AIDS
pmed.0020061.txt:        The US EPA has been slower than the EU to adapt to the overwhelming evidence that
pmed.0020247.txt:        stigmatized as the vectors of HIV transmission, despite overwhelming evidence to the
```
This command ensures that we only get lines that have the whole word "overwhelming" but not just the word "over" or something else in the files in plos folder.
