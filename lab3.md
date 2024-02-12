Failure inducing input
```
int[] input2 = { 3, 2, 1 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 1, 2, 3 }, input1);
```
Output of above input
![Image](OutputFailure.png)
Input that doesn't induce failure
```
int[] input1 = { 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3 }, input1);
```
Output of above input
![Image](OutputSuccess.png)
Code before fix
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
Code after fix
```
static void reverseInPlace(int[] arr) {
    int[] newArr = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        newArr[i] = arr[arr.length - i - 1];
    }
    for(int j = 0; j < arr.length; j += 1) {
        arr[j] = newArr[j];
    }
}
```

```
less -N find-biomed.txt

      1 biomed/
      2 biomed/1468-6708-3-1.txt
      3 biomed/1468-6708-3-10.txt
      4 biomed/1468-6708-3-3.txt
      5 biomed/1468-6708-3-4.txt
      6 biomed/1468-6708-3-7.txt
      7 biomed/1471-2091-2-10.txt
      8 biomed/1471-2091-2-11.txt
      9 biomed/1471-2091-2-12.txt
     10 biomed/1471-2091-2-13.txt
     11 biomed/1471-2091-2-16.txt
find-biomed.txt
```
```
less -N biomed/1471-2091-3-15.txt

      1
      2
      3
      4
      5         Background
      6         Sequence homology between the serotonin type 3 receptor
      7         (5-HT
      8         3 R), the nicotinic acetylcholine
      9         receptor (nAChR), the GABA
     10         A receptor and the glycine receptor
     11         suggests a large amount of structural similarity within
biomed/1471-2091-3-15.txt
```
```
less -p "3-19" find-biomed.txt

biomed/1471-2121-3-19.txt
biomed/1471-2121-3-2.txt
biomed/1471-2121-3-21.txt
biomed/1471-2121-3-22.txt
biomed/1471-2121-3-25.txt
biomed/1471-2121-3-30.txt
biomed/1471-2121-3-4.txt
biomed/1471-2121-3-6.txt
biomed/1471-2121-3-8.txt
biomed/1471-2121-4-1.txt
biomed/1471-2121-4-2.txt
find-biomed.txt
```
```
less -p "paper" biomed/1468-6708-3-1.txt

        events [ 10 ] . In this paper we study whether BMI at
        baseline is associated with living longer, and/or with more
        years of being healthy, in a cohort of older adults for
        whom risk factors, subclinical disease, and morbidity are
        well characterized. The goal is to determine whether
        analyses based on years of life (YOL) or on YHL would
        provide substantively different results, and which measure
        would yield more powerful evaluations of weight
        modification interventions in older adults.


biomed/1468-6708-3-1.txt
```
```
less -M find-plos.txt

plos/
plos/journal.pbio.0020001.txt
plos/journal.pbio.0020010.txt
plos/journal.pbio.0020012.txt
plos/journal.pbio.0020013.txt
plos/journal.pbio.0020019.txt
plos/journal.pbio.0020028.txt
plos/journal.pbio.0020035.txt
plos/journal.pbio.0020040.txt
plos/journal.pbio.0020042.txt
plos/journal.pbio.0020043.txt
plos/journal.pbio.0020046.txt
find-plos.txt lines 1-12/253 5%
```
```
less -M plos/journal.pbio.0020046.txt

        Stuttering, with its characteristic disruption in verbal fluency, has been known for
        centuries; earliest descriptions probably date back to the Biblical Moses' “slowness of
        speech and tongue” and his related avoidance behavior (Exodus 4, 10–13). Stuttering occurs
        in all cultures and ethnic groups (Andrews et al. 1983; Zimmermann et al. 1983), although
        prevalence might differ. Insofar as many of the steps in how we produce language normally
        are still a mystery, disorders like stuttering are even more poorly understood. However,
        genetic and neurobiological approaches are now giving us clues to causes and better
plos/journal.pbio.0020046.txt lines 1-12/232 4%
```
```
less -F plos/pmed.0020191.txt





        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
        Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against
        biohistorical research; instead, it points out that such investigations are currently
        taking place without guidelines—ethical, scientific, moral, or religious. The question
        remains: if such guidelines were to be established, what individuals, institutions,
        governments, medical examiners, family members, or intrepid biographers are to be given
        permission? Who is to decide what is “historically significant”? Not to mention the
        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
        comments [2] implied that they took a position on this issue.




xchua@Aegis MINGW64 ~/Documents/Github/docsearch/technical (main)
```
```
less -F  find-AlcoholProblems.txt
government/Alcohol_Problems/
government/Alcohol_Problems/DraftRecom-PDF.txt
government/Alcohol_Problems/Session2-PDF.txt
government/Alcohol_Problems/Session3-PDF.txt
government/Alcohol_Problems/Session4-PDF.txt

xchua@Aegis MINGW64 ~/Documents/Github/docsearch/technical (main)
```
