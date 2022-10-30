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
**Why It's Useful:**
* The `-N` option for the `less` command displays the line numbers of the file being opened.

**Command 1.2**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -N biomed/1471-2105-3-26.txt
```        

**Output 1.2**
```
    332         literature. We detected a small increase in expression of 
    333         ICAM1 ( 
    334         intercellular adhesion molecule 1 )
    335         in CC (Fold-change = 1.9, p-value = 0.0081), which was also
    336         consistent with the literature [ 17 ] .
    337         The expression results for the genes 
    338         JUN ( 
    339         c-jun ) and 
    340         VHL ( 
    341         von Hippel-Lindau ) did not match the
    342         literature [ 18 19 ] . Nor did the result for 
    343         KRT7 ( 
    344         cytokeratin 7 ), which has been shown
    345         to be overexpressed in Chr [ 20 ] . Instead we found 
    346         KRT7 to be strongly repressed in CC
:
``` 
**Why It's Useful:**
* This option can be useful for referencing specific lines in the text, especially in large files

**Command 1.3**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -N government/Env_Prot_Agen/ctf1-6.txt
```
**Output 1.3**
```
   2088 organisms. If the acclimation process is repeated with a new group
   2089 of test organisms and excessive mortality occurs, it is recommended
   2090 that an alternative source of dilution water be used.
   2091 
   2092 
   2093 6.7
   2094 TEST ORGANISM DISPOSAL
   2095 
   2096 
   2097 6.7.1 When the toxicity test(s) is concluded, all test organisms
   2098 (including controls) should be humanely destroyed and disposed of
   2099 in an appropriate manner.
   2100 
   2101 
   2102 
(END)
```
**Why It's Useful:**

* The option also manually shows the user how many lines are in the file (and which of them contain content).

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
**Why It's Useful:**
* The `-M` option for `less` shows a lot more information about the file when reading it
* The manual of the option describes it to be similar to the `more` command.

**Command 2.2**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -M biomed/1471-2105-2-8.txt 
```
**Output 2.2**
```
by structural RNA evolution; (3) allowing gapped
        alignments; and (4) allowing for the possibility that only
        part of the pairwise alignment may represent a coding
        region or structural RNA, because a primary sequence
        alignment may extend into flanking noncoding or
        nonstructural conserved sequence. These extensions add
        complexity to the approach. We use probabilistic modeling
        methods and formal languages to guide our construction. We
        use "pair hidden Markov models" (pair-HMMs) (introduced in
        [ 18 ] ) and a "pair stochastic context free grammar"
        (pair-SCFG) (a natural extension of the pair-HMM idea to
        RNA structure) to produce three evolutionary models for
        "coding", "structural RNA", or "something else" (a null
        hypothesis). Given three probabilistic models and a
        pairwise sequence alignment to be tested, we can calculate
biomed/1471-2105-2-8.txt lines 64-78/1495 6% 
```
**Why It's Useful:**
* This option is useful for providing information about the file as its being processed, such as the lines currently being read and the percentage of the file that has been read so far.

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
* Without this option, there is no way to know how much of the file has been read while in the `less ` window.
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
**Why It's Useful:**
* This option changes the format of `less` for any lines that are longer than the viewing window. 
* Normally, the line wraps into the next line, which can be confusing to see. Instead, the `-S` option cuts off each line and assures the file is shown exactly as originally created.

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
**Why It's Useful:**
* For files that have very long lines, it's often useful to have its entire contents stored on a single line in the viewing window. 

**Command 3.3**
```
arnavkamra@Arnavs-MacBook-Pro technical % less -S government/Alcohol_Problems/Session4-PDF.txt
```
**Output 3.3**
```
counseling are often
provision of alcohol
D) may provide an
currently not actively
wareness of their problem,
r treatment on their

vely to be effective.1
ment. Studies suggest that
ze on the motivating
itions that require
e need for behavior
ts who have not yet
:
```
**Why It's Useful:**
* It becomes easier to keep track of each line, since you can view the cut-off portion of the line with the right arrow key.
