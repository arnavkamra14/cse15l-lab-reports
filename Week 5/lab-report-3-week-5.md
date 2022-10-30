# Week 5 Lab Report
## *less* command-line option 1: -N
**Command 1.1:**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -N 911report/chapter-13.1.txt
```
**Output 1.1:**
```
      1 
      2     
      3         
      4             HOW TO DO IT? A DIFFERENT WAY OF ORGANIZING THE GOVERNMENT
      5             As presently configured, the national security institutions of       5 the U.S. government
      6                 are still the institutions constructed to win the Cold War.      6  The United States
      7                 confronts a very different world today. Instead of facing a      7  few very dangerous
      8                 adversaries, the United States confronts a number of less v      8 isible challenges that
:
```
**Command 1.2**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -N government/Post_Rate_Comm/Cohenetal_Scale.txt
```        

**Output 1.2**
```
      1 
      2 
      3 
      4 
      5 A MEASURE OF SCALE ECONOMIES FOR POSTAL SYSTEMS
      6 ROBERT H. COHEN
      7 
      8 U. S. POSTAL RATE COMMISSION
      9 EDWARD H. CHU
     10 U.S. ENVIRONMENTAL PROTECTION AGENCY
     11 
     12 PUBLISHED IN MANAGING CHANGE IN THE POSTAL DELIVERY INDUSTRIES,
:
``` 
**Command 1.3**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -N plos/journal.pbio.0020147.txt
```
**Output 1.3**
```
      8         evolutionary theory is incomplete and that, in consequence, we are       8 failing fully to
      9         understand phenomena as disparate as ecosystem development and the 
      9 interplay of genes and
     10         culture in shaping human evolution. What we are missing, they argue
     10 , is an appreciation of
     11         niche construction, the process by which an organism modifies the a
     11 biotic and biotic
     12         environment in which it is subject to natural selection. The author
     12 s' major assertion is
     13         that the importance of niche construction is so great that it shoul
     13 d be regarded “after
:
```
**Why It's Useful:**
* The `-N` option for the `less` command displays the line numbers of the file bein opened.
* This command can be useful for referencing specific lines in the text, especially in large files, as well as manually showing the user how many lines are in the file (and which of them contain content)

---

## *less* command-line option 2: -M

**Command 2.1**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -M plos/journal.pbio.0020012.txt
```
**Output 2.1**
```
f extending
        lifespan. The most proficient of the group is resveratrol, the plant polyph
enol found in
        red wine, and its discovery as a potential elixir to combat ageing represen
ts another
        extraordinary advance in a decade of discoveries that have revolutionised t
he field.
        
          
            “These molecules will be useful for treating diseases associated with
            ageing, like diabetes and Alzheimer's.”
          
plos/journal.pbio.0020012.txt lines 17-25/225 9%
```
**Command 2.2**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -M biomed/1471-2105-2-8.txt 
```
**Output 2.2**
```
          b 
          2 
          b 
          3 | 
          t ), for some divergence "time" 
          t , are derived from the chosen
          substitution matrix (i.e. the choice of matrix defines 
          t ). We make an independence
          assumption that the conditional probability of each codon
          depends only on its own encoded amino acid - i.e., it
          does not depend on the the other codon - so we can use
          the approximation
biomed/1471-2105-2-8.txt lines 341-352/1495 21%
```
**Command 2.3**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -M government/About_LSC/ODonnell_et_al_v_LSCdecision.txt  
```
**Output 2.3**
```
in the coalfields region of southwestern Virginia, has been an LSC
grantee since 1980.
O'DONNELL v. EIDLEMAN
This litigation involves CCLS's challenge to certain actions
taken by the LSC in connection with the LSC's consolidation of
services areas (undertaken as a cost-cutting measure) and
implementation of a competitive bidding program for grant money.
Following a bench trial, the district court rejected CCLS's claims
on the merits.
II.
In our recent decision in Regional Management Corp. v. Legal
Services Corp., 186 F.3d 457 (4th Cir. 1999), we concluded that a
government/About_LSC/ODonnell_et_al_v_LSCdecision.txt lines 58-69/130 45%
```
**Why It's Useful:**
* The `-M` option for `less` shows a lot more information about the file when reading it, similar to the `more` command.
* This option is useful for providing information about the file as its being processed, such as the lines currently being read and the percentage of the file that has been read so far.
* Without this option there is no way to know how much of the file has been read.
---

## *less* command-line option 3: -S

**Command 3.1**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -S plos/journal.pbio.0020040.txt
```
**Output 3.1**
```
 For people who received their introduction to cancer genetics in college in
        half of the 1990s, everything looked simple and straightforward. It was the
        explain to sincerely interested relatives who wanted to know what you were 
        time on. There were oncogenes and there were tumour suppressor genes. Oncog
        overactive genes and proteins that somehow caused cancer because they were 
        therefore, they were dominant. Tumour suppressor genes were genes that woul
        prevent a tumour from happening and that needed to be inactivated for a tum
        form; both copies of a tumour suppressor gene had to be inactivated, and th
        recessive. If inactivation of these genes is a random process, it was under
        people who inherit an inactivated copy of a tumour suppressor gene had a hi
        developing the associated form(s) of cancer than people born with two norma
        postulated in Alfred Knudson's (1971) two-hit model. And, indeed, it was sh
:
```
**Command 3.2**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -S biomed/1471-2091-3-13.txt    
```
**Output 3.2**
```
Background
        
        Escherichia coli DNA topoisomerase I
        is a representative example of type IA DNA topoisomerase
        (for reviews, see refs [ 1 2 ] ). Its major biological role
        in the bacterial cell is the removal of excessive negative
        supercoils from DNA to maintain the DNA at optimal
        superhelical density along with DNA gyrase [ 3 ] . The
        enzyme has a molecular weight of 97 kDa and the active site
        tyrosine responsible for DNA cleavage is found in the 67
        kDa N-terminal transesterification domain. The structure of
:
```
**Command 3.3**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -S government/Alcohol_Problems/Session4-PDF.txt
```
**Output 3.3**
```
Session 4.
Implementing Preventive Interventions in
Emergency Medicine: Strategic Considerations

Larry M. Gentilello, MD
Individuals who may benefit from alcohol counseling are often
unaware of their need for treatment. The provision of alcohol
interventions in emergency departments (ED) may provide an
opportunity to treat individuals who are currently not actively
seeking such care. Due to their lack of awareness of their problem,
these patients are unlikely to present for treatment on their
own.
Treatment does not need to be sought actively to be effective.1
How-ever, motivation can facilitate treatment. Studies suggest that
:
```
**Why It's Useful:**
* This option changes the format of `less` for any lines that are longer than the viewing window. Normally, the line wraps into the next line, which can be confusing to see. Instead, the `-S` command cuts off each line and assures the file is shown exactly as originally created.
* For files that have very long lines, it's often useful to have its entire contents stored on a single line in the viewing window. 
* It becomes easier to keep track of each line, since you can view the cut-off portion of the line with the right arrow key.
