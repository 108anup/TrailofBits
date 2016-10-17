# TrailofBits
Some Trivia and Useful Links I browse through frequently

## Common Workarounds and Tricks/Tips  
http://lifehacker.com/5743814/become-a-command-line-ninja-with-these-time-saving-shortcuts

## Competitve Coding
http://bigocheatsheet.com/  
http://codeforces.com/blog/entry/13529  
https://www.quora.com/What-are-some-algorithms-and-data-structures-which-should-definitely-be-included-in-ones-ACM-ICPC-team-notebook  
https://www.topcoder.com/community/data-science/data-science-tutorials/  
http://visualgo.net/  
https://www.hackerearth.com/notes/getting-started-with-the-sport-of-programming/  
http://web.stanford.edu/class/cs97si/  
http://codeforces.com/blog/entry/23054  
https://discuss.codechef.com/questions/48877/data-structures-and-algorithms  
https://web.stanford.edu/~liszt90/acm/notebook.html  

## Hacking
https://trailofbits.github.io/ctf/    
https://backdoor.sdslabs.co/   
https://web.stanford.edu/~adyuen/107 -> Mercurial, Valgrind, GDB, IA32  
https://www.seas.upenn.edu/cets/answers/auth-htpasswd.html  

## Programming Languages
### Python
string urllib2.quote(string)  
eg. converts "@" to "%40"  
unquote does the opposite.  

int ord(char) returns ascii value to char input  

type python in command line to open python command line interpreter  
python file.py runs Python Interpreter with file.py as input file.  

a, b = map(int, input().split()) # To Read Integeres Separated by Space  

Pass by Assignment: http://stackoverflow.com/a/986145/5039326  

### C++
char* pStr = "text";  
cout <<  pStr << endl; // -> text  
cout << *pStr << endl; // -> t  
cout << &pStr << endl; // -> 0012FF48  
cout << (void*) pStr <<endl; // -> Address pointed by pStr  
pStr[0]='a'; //RunTime Error  
*(pStr)='a'; //RunTime Error  
//i.e. const strings are immutable  

### C
To input strings in C, use fgets();  
fgets(char[],size_t,stdin);  
or use:  
scanf("%[^\n]%*c",string); or scanf("[^\n]%c",string,separator);  //Recommended   
'*' is the suppression character, means take input but don't assign to any variable.  
%[abc] is a search set everything except  
  
input formatting:  
scanf("%d%d",&var1,&var2);  
scanf("%d %d",&var1,&var2); have same effect  
scanf("%d,%d",&var1,&var2); delimiter is set as ','  
scanf("%d%d%n%d%d",&x,&y,&count,&z,&w);  
count stores number of charcters read just before encountering it including newlines  
for %c leading whitespaces are not ignored.  
only after assigning the value to variables, count of characters processed(assigned+ignored) till that point are removed.  

scanf stops/ changes at delimiter or when input can't be converted or when given width has been read or entry outside search set is entered.  
scanf entirely stops scanning when Next input character has conflict with corresponding non-whitespace  
character in the format string or Next character is EOF or Format string is exhausted.  
Therefore, If a character sequence that is not a part of format specifier occurs in the format string, it must match the current sequence of characters in the input field.  

### Competitive Coding
while using cin/cout put in main:  
std::ios_base::sync_with_stdio(false); //makes stdio io and iostream operations of comparable speed  
cin.tie(0); //cancel flush with every cout  

for endless input  
use while(cin>>exp)  
or  while(scanf("%s",exp))  

for dp with more than 1e7 elements use memoization.  

scanf("%llu",&var); //input unsigned long long  
scanf("%lld",&var); //input signed long long  
scanf("%lu",&var); //input unsigned long  


### BASH

http://serverfault.com/questions/259339/bash-variable-loses-value-at-end-of-while-read-loop/259342#259342  
Piping creates a new child process and thus variables are different in the processes use brackets to extend the scope of the process.  

http://unix.stackexchange.com/questions/99185/what-do-square-brackets-mean-without-the-if-on-the-left  
[ is a built-in while [[ is a keyword  

http://www.tldp.org/LDP/abs/html/special-chars.html  
Answer to most of your Questions.  

## Basic Git  
Conventions:  
default branch - master  
The local repo = local  
Remote your version = origin  
Remote collaborative = upstream  

git diff //diff between staged and working directory  
git diff --cached //diff between staged and last commit (there may be things in working directory not yet staged being tracked)  
git diff HEAD //union of above 2 (diff between HEAD and working directory)  
git diff HEAD^ //diff between head ans last to last commit.  
none shows untracked differences  
  
commit - staged changes - working directory (tracked and unstaged). (FLow of Files)  

git rebase -i HEAD~x //x = number  
to choose certain commits and discard others or to squash commits etc.  
  
git checkout -b branch-name //create branch-name and checkout  
git checkout branch-name //checkout branch  
git checkout <commit> //HEAD detach and view earlier commit  
git checkout master // reattach HEAD after viewing old commit  
git revert <commit> // removes commit given by hash code and whatever remains is left in a new commit  
git reset --hard HEAD~1 //Completely undo last commit (no retaining back) 
  
git add -u //stages tracked - (changed or removed)  
git add .  //stages untracked new, tracked - (changed)  
git add -a //both of above  

(http://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide)  
