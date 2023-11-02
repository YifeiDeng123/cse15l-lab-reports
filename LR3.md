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
(1) grep -c: It displays the count of matching lines instead of the actual lines
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
This command line prints a count of lines in each file in the folder government/About_LSC that contains the word "gender". By using this command, we can know which file is talking about the gender topic and which file considers more about the gender topic.
