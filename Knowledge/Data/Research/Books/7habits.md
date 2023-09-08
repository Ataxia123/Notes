https://www.moolenaar.neSeven 

## Habits of effective text editing

Bram Moolenaar
November 2000
If you spend a lot of time typing plain text, writing programs or HTML, you can save much of that time by using a good editor and using it effectively. This paper will present guidelines and hints for doing your work more quickly and with fewer mistakes.

The open source text editor Vim (Vi IMproved) will be used here to present the ideas about effective editing, but they apply to other editors just as well. Choosing the right editor is actually the first step towards effective editing. The discussion about which editor is the best for you would take too much room and is avoided. If you don't know which editor to use or are dissatisfied with what you are currently using, give Vim a try; you won't be disappointed.

[Vim commands and options are printed in this font]
Part 1: edit a file
1. Move around quickly

Most time is spent reading, checking for errors and looking for the right place to work on, rather than inserting new text or changing it. Navigating through the text is done very often, thus you should learn how to do that quickly.

Quite often you will want to search for some text you know is there. Or look at all lines where a certain word or phrase is used. You could simply use the search command /pattern to find the text, but there are smarter ways:

If you see a specific word and want to search for other occurrences of the same word, use the * command. It will grab the word from under the cursor and search for the next one.
If you set the 'incsearch' option, Vim will show the first match for the pattern, while you are still typing it. This quickly shows a typo in the pattern.
If you set the 'hlsearch' option, Vim will highlight all matches for the pattern with a yellow background. This gives a quick overview of where the search command will take you. In program code it can show where a variable is used. You don't even have to move the cursor to see the matches.
In structured text there are even more possibilities to move around quickly. Vim has specific commands for programs in C (and similar languages like C++ and Java):

Use % to jump from an open brace to its matching closing brace. Or from a "#if" to the matching "#endif". Actually, % can jump to many different matching items. It is very useful to check if () and {} constructs are balanced properly.
Use "[]" to jump back to the "{" at the start of the current code block.
Use gd to jump from the use of a variable to its local declaration.
There are many more, of course. The point is that you need to get to know these commands. You might object that you can't possibly learn all these commands - there are hundreds of different movement commands, some simple, some very clever - and it would take weeks of training to learn them all. Well, you don't need to; instead realize what your specific way of editing is, and learn only those commands that make your editing more effective.

There are three basic steps:

While you are editing, keep an eye out for actions you repeat and/or spend quite a bit of time on.
Find out if there is an editor command that will do this action quicker. Read the documentation, ask a friend, or look at how others do this.
Train using the command. Do this until your fingers type it without thinking.
Let's use an example to show how it works:

You find that when you are editing C program files, you often spend time looking for where a function is defined. You currently use the * command to search for other places where the function name appears, but end up going through a lot of matches for where the function is used instead of defined. You get the idea that there must be a way to do this faster.
Looking through the quick reference you find a remark about jumping to tags. The documentation shows how this can be used to jump to a function definition, just what you were looking for!
You experiment a bit with generating a tags file, using the ctags program that comes with Vim. You learn to use the CTRL-] command, and find you save lots of time using it. To make it easier, you add a few lines to your Makefile to automatically generate the tags file.
A couple of things to watch out for when you are using these three steps:

"I want to get the work done, I don't have time to look through the documentation to find some new command". If you think like this, you will get stuck in the stone age of computing. Some people use Notepad for everything, and then wonder why other people get their work done in half the time...
Don't overdo it. If you always try to find the perfect command for every little thing you do, your mind will have no time left to think about the work you were actually doing. Just pick out those actions that take more time than necessary, and train the commands until you don't need to think about it when using them. Then you can concentrate on the text.
In the following sections there will be suggestions for actions that most people have to deal with. You can use these as inspiration for using the three basic steps for your own work.

2. Don't type it twice

There is a limited set of words we type. And even a limited number of phrases and sentences. Especially in computer programs.  Obviously, you don't want to type the same thing twice.

Very often you will want to change one word into another. If this is to be done in the whole file, you can use the :s (substitute) command. If only a few locations needs changing, a quick method is to use the * command to find the next occurrence of the word and use cw to change the word. Then type n to find the next word and . (dot) to repeat the cw command.

The . command repeats the last change. A change, in this context, is inserting, deleting or replacing text. Being able to repeat this is a very powerful mechanism. If you organise your editing around it, many changes will become a matter of hitting just that . key. Watch out for making other changes in between, because it will replace the change that you were repeating. Instead you might want to mark the location with the m command, continue your repeated change and come back there later.

Some function and variable names can be awkward to type. Can you quickly type "XpmCreatePixmapFromData" without a typo and without looking it up? Vim has a completion mechanism that makes this a whole lot easier. It looks up words in the file you are editing, and also in #include'd files. You can type "XpmCr", then hit CTRL-N and Vim will expand it to "XpmCreatePixmapFromData" for you. Not only does this save quite a bit of typing, it also avoids making a typo and having to fix it later when the compiler gives you an error message.

When you are typing a phrase or sentence multiple times, there is an even quicker approach. Vim has a mechanism to record a macro. You type qa to start recording into register 'a'. Then you type your commands as usual and finally hit q again to stop recording. When you want to repeat the recorded commands you type @a. There are 26 registers available for this.

With recording you can repeat many different actions, not just inserting text. Keep this is mind when you know you are going to repeat something.

One thing to watch out for when recording is that the commands will be played back exactly as you typed them. When moving around you must keep in mind that the text you move over might be different when the command is repeated. Moving four characters left might work for the text where you are recording, but it might need to be five characters where you repeat the commands. It's often necessary to use commands to move over text objects (words, sentences) or move to a specific character.

When the commands you need to repeat are getting more complicated, typing them right at once is getting more difficult. Instead of recording them, you should then write a script or macro. This is very useful to make templates for parts of your code; for example, a function header. You can make this as clever as you like.

3. Fix it when it's wrong

It's normal to make errors while typing. Nobody can avoid it. The trick is to quickly spot and correct them. The editor should be able to help you with this. But you need to tell it what's wrong and what's right.

Very often you will make the same mistake again and again. Your fingers just don't do what you intended. This can be corrected with abbreviations. A few examples:

:abbr Lunix Linux
:abbr accross across
:abbr hte the
The words will be automatically corrected just after you typed them.
The same mechanism can be used to type a long word with just a few characters. Especially useful for words that you find hard to type, and it avoids that you type them wrong. Examples:

:abbr pn penguin
:abbr MS Mandrake Software
However, these tend to expand to the full word when you don't want it, which makes it difficult when you really want to insert "MS" in your text. It is best to use short words that don't have a meaning of their own.

To find errors in your text Vim has a clever highlighting mechanism. This was actually meant to be used to do syntax highlighting of programs, but it can catch and highlight errors as well.

Syntax highlighting shows comments in colour. That doesn't sound like an important feature, but once you start using it you will find that it helps a lot. You can quickly spot text that should be a comment, but isn't highlighted as such (you probably forgot a comment marker).Or see a line of code highlighted as comment (you forgot to insert a "*/"). These are errors which are hard to spot in a B&W file and can waste a lot of time when trying to debug the code.

The syntax highlighting can also catch unbalanced braces. An unbalanced ")" is highlighted with a bright red background. You can use the % command to see how they match, and insert a "(" or ")" at the right position.

Other common mistakes are also quickly spotted, for example using "#included <stdio.h>" instead of "#include <stdio.h>". You easily miss the mistake in B&W, but quickly spot that "include" is highlighted while "included" isn't.

A more complex example: for English text there is a long list of all words that are used. Any word not in this list could be an error. With a syntax file you can highlight all words that are not in the list. With a few extra macros you can add words to the wordlist, so that they are no longer flagged as an error. This works just as you would expect in a word processor. In Vim it is implemented with scripts and you can further tune it for your own use: for example, to only check the comments in a program for spelling errors.

Part 2: edit more files
4. A file seldom comes alone

People don't work on just one file. Mostly there are many related files, and you edit several after each other, or even several at the same time. You should be able to take advantage of your editor to make working with several files more efficient.

The previously mentioned tag mechanism also works for jumping between files. The usual approach is to generate a tags file for the whole project you are working on. You can then quickly jump between all files in the project to find the definitions of functions, structures, typedefs, etc. The time you save compared with manually searching is tremendous; creating a tags file is the first thing I do when browsing a program.

Another powerful mechanism is to find all occurrences of a name in a group of files, using the :grep command. Vim makes a list of all matches, and jumps to the first one. The :cn command takes you to each next match. This is very useful if you need to change the number of arguments in a function call.

Include files contain useful information. But finding the one that contains the declaration you need to see can take a lot of time. Vim knows about include files, and can search them for a word you are looking for. The most common action is to lookup the prototype of a function. Position the cursor on the name of the function in your file and type [I: Vim will show a list of all matches for the function name in included files. If you need to see more context, you can directly jump to the declaration. A similar command can be used to check if you did include the right header files.

In Vim you can split the text area in several parts to edit different files. Then you can compare the contents of two or more files and copy/paste text between them. There are many commands to open and close windows, jump between them, temporarily hide files, etc. Again you will have to use the three basic steps to select the set of commands you want to learn to use.

There are more uses of multiple windows. The preview-tag mechanism is a very good example. This opens a special preview window, while keeping the cursor in the file you are working on. The text in the preview window shows, for example, the function declaration for the function name that is under the cursor. If you move the cursor to another name and leave it there for a second, the preview window will show the definition of that name. It could also be the name of a structure or a function which is declared in an include file of your project.

5. Let's work together

An editor is for editing text. An e-mail program is for sending and receiving messages. An Operating System is for running programs. Each program has its own task and should be good at it. The power comes from having the programs work together.

A simple example: You need to write a summary of no more than 500 words. Select the current paragraph and write it to the "wc" program: vip:w !wc -w. The external "wc -w" command is used to count the words. Easy, isn't it?

There will always be some functionality that you need that is not in the editor. Making it possible to filter text with another program means you can Add that functionality externally. It has always been the spirit of Unix to have separate programs that do their job well, and work together to perform a bigger task. Unfortunately, most editors don't work too well together with other programs - you can't replace the e-mail editor in Netscape with another one, for example. You end up using a crippled editor. Another tendency is to include all kinds of functionality inside the editor; Emacs is a good example of where this can end up. (Some call it an operating system that can also be used to edit text.)

Vim tries to integrate with other programs, but this is still a struggle. Currently it's possible to use Vim as the editor in MS-Developer Studio and Sniff. Some e-mail programs that support an external editor, like Mutt, can use Vim. Integration with Sun Workshop is being worked on. Generally this is an area that has to be improved in the near future. Only then will we get a system that's better than the sum of its parts.

6. Text is structured

You will often work with text that has some kind of structure, but different from what is supported by the available commands. Then you will have to fall back to the "building blocks" of the editor and create your own macros and plugins to work with this text. We are getting to the more complicated stuff here.

One of the simpler things is to speed up the edit-compile-fix cycle. Vim has the :make command, which starts your compilation, catches the errors it produces and lets you jump to the error locations to fix the problems. If you use a different compiler, the error messages will not be recognised. Instead of going back to the old "write it down" system, you should adjust the 'errorformat' option. This tells Vim what your errors look like and how to get the file name and line number out of them. It works for the complicated gcc error messages, thus you should be able to make it work for almost any compiler.

Sometimes adjusting to a type of file is just a matter of setting a few options or writing a few macros. For example, to jump around manual pages, you can write a macro that grabs the word under the cursor, clears the buffer and then reads the manual page for that word into the buffer. That's a simple and efficient way to lookup cross-references.

Using the three basic steps, you can work more effectively with any sort of structured file. Just think about the actions you want to do with the file, find the editor commands that do it and start using them. It's really as simple as it sounds. You just have to do it.

Part 3: sharpen the saw
7. Make it a habit

Learning to drive a car takes effort. Is that a reason to keep driving your bicycle? No, you realize you need to invest time to learn a skill. Text editing isn't different. You need to learn new commands and turn them into a habit.

On the other hand, you should not try to learn every command an editor offers. That would be a complete waste of time. Most people only need to learn 10 to 20 percent of the commands for their work. But it's a different set of commands for everybody. It requires that you lean back now and then, and wonder if there is some repetitive task that could be automated. If you do a task only once, and don't expect having to do it again, don't try to optimise it. But you probably realize you have been repeating something several times in the last hour. Then search the documentation for a command that can do it quicker. Or write a macro to do it.  When it's a larger task, like lining out a specific sort of text, you could look around in newsgroups or on the Internet to see if somebody already solved it for you.

The essential basic step is the last one. You can think of a repetitive task, find a nice solution for it and after the weekend you forgot how you did it. That doesn't work. You will have to repeat the solution until your fingers do it automatically. Only then will you reach the efficiency you need. Don't try to learn too many things at once. But doing a few at the same time will work well. For tricks you don't use often enough to get them in your fingers, you might want to write them down to be able to look them up later. Anyway, if you keep the goal in view, you will find ways to make your editing more and more effective.

One last remark to remind you of what happens when people ignore all the above: I still see people who spend half their day behind a VDU looking up at their screen, then down at two fingers, then up at the screen, etc. - and then wonder why they get so tired... Type with ten fingers! It's not just faster, it also is much less tiresome. Using a computer program for one hour each day, it only takes a couple of weeks to learn to touch-type.

Epilogue
The idea for the title comes from the successful book "The 7 habits of highly effective people" by Stephen R. Covey. I recommend it to everyone who wants to solve personal and professional problems (and who doesn't?). Although some of you will claim it came from the Dilbert book "Seven years of highly defective people" by Scott Adams (also recommended!). See http://iccf-holland.org/click1.html and go to "recommended books and CDs".

About the author
Bram Moolenaar is the main author of Vim. He writes the core Vim functionality and selects what code submitted by many others is included. He graduated at the technical university of Delft as a computer technician. Now he mainly works on software, but still knows how to handle a soldering iron. He is founder and treasurer of ICCF Holland, which helps orphans in Uganda. He does freelance work as a systems architect, but actually spends most time working on Vim. His e-mail address: Bram AT Moolenaar.net.t/habits.html


```
Locality Date Sex Range TL (cm) Cause of death
Naptunia Feb- 13 female 99 entangled
Pinar Dec- 13 male 127 entangled
Neptunia Apr- 14 male 119 stranding
Sanra Lucia del Este Jun- 14 feamle 114 stranding
Jaureguiberry Jul- 14 male 146 stranding
Piriapolis Oct- 14 female 92 stranding
Valisas Nov- 14 female 87 stranding
Solis Dec- 14 female 110 entangled
Aguas Dulces Dec- 14 male 134 stranding
Valisas Jan- 15 female 103 stranding
Cuchilla Alta Feb- 15 female 88 stranding
```

Pinar Mar- 15 female 84 entangled
Pinar May- 15 male 152 stranding
Montevideo Aug- 15 female 105 entangled
Montevideo Oct- 15 female 95 entangled
Barra del Chuy Oct- 15 female 129 stranding
Cuchilla Alta Nov- 15 male 120 stranding
La Coronilla Nov- 15 male 133 stranding
Montevideo Jun- 16 male 136 stranding
Montevideo Jul- 16 male 105 entangled
Montevideo Jul- 16 female 95 entangled
Montevideo Jul- 16 female 154 entangled
Santa Lucia del Este Jul- 16 female 110 stranding
Montevideo Jul- 16 female 149 stranding
Montevideo Aug- 16 female 105 stranding
Pinar Aug- 16 male 95 stranding
Montevideo Aug- 16 female 154 stranding
Montevideo Aug- 16 female 164 stranding
Montevideo Sep- 16 female 152 stranding
San Luis Sep- 16 male 147 stranding
San Luis Sep- 16 female 165 stranding
Pinar Sep- 16 male 129 stranding
Piriapolis Sep- 16 male 111 stranding
Piriapolis Sep- 16 female 147 stranding
La Paloma Sep- 16 female 136 stranding
La Paloma Sep- 16 male 106 stranding
Jose Ignacio Sep- 16 male 113 entangled
Piriapolis Oct- 16 male 93 entangled
Pinar Oct- 16 male 105 entangled
Pinar Oct- 16 female 115 entangled
Pinar^ Oct-^16 female^121 entangled^

The relationship between the Franciscana dolphin total length (FTL) and prey total length
(PTL) was analyzed using linear regressions (Sokal and Rohlf 1995). The frequency of
occurrence (%FO) was calculated as the number of stomachs in which prey occurred, the
numerical abundance (%N) as the number of individuals of each prey type / total number of


individuals of all prey types, and the reconstructed biomass (%W) as the biomass of each prey
type / total biomass represented by all prey; all these indexes were expressed as percentages
(Hyslop 1981, Castley et al. 1991, Cortés 1997). The relative importance of prey species was
evaluated using the index of relative importance (IRI) calculated as IRI = [%N+%W] * %FO and
then transformed as percentage (%IRI) (Pinkas et al., 1971; Hyslop 1981).
Diet diversity was analyzed using Shannon diversity index H (H = -Σ (ni n-1) ln (ni n-1),
where ni = number of individuals of the species in a sample and n = total number of individuals
registered in the sample), Shannon equitability (H/ln(S), S = total richness of the sample) and
Berger Parker species richness (d= Nmax/N where Nmax is the number of individuals in the
most abundant species, and N is the total number of individuals in the sample) (Magurran 2004).
Lower and upper percentiles 25% and 75% of the indices were calculated using bootstrap for the
stomach sampled. Specialization diet was analyzed using Levin’s index (niche breadth)
standardized by the Hulbert (1978) method. This index varies between 0 and 1 and the predator
is considered specialist when the value is close to zero and generalist when it is close to 1
(Ludwig & Reynolds 1988).In all cases, the significance level considered was p = 0.05. The
statistical software PAST (Hammer et al 2001) was used for all statistical analyses and diversity
index.
Results
Prey consumption: stomach contents analysis
The measured total length of the Franciscana dolphins included in this study ranged between 84
and 165 cm (Table 1). From the 41 stomachs sampled only 4 were empty.


A total of nine food items in fresh condition or in the beginning of digestion were identified: the
striped weakfish Cynoscion guatucupa (Cuvier 1830), the whitemouth croaker Micropogonias
furnieri (Desmarest 1823), the argentine croaker Umbrina canossai (Berg 1895) the banded
croaker Paralonchorus brasiliensis (Steindachner 1875), Southern King Weakfish Macrodon
articauda (Günther, 1880), all species belonging to the family Sciaenidae; the toadfish
Porichthys porosissimus (Valenciennes 1837) (Family Batrachoididae), the Atlantic anchovy
Engraulis anchoita (Hubbs & Marini 1935) (Family Engraulidae), Brazilian codling Urophycis
brasiliensis (Kaup, 1858). The squid Loligo sanpaulensis (Brakoniecki 1984) (Family
Loligindae) (Table 2) was only detected in one stomach. In eight stomachs unidentified rest (UI)
was found (Table 2). The UI was not taken into account in the quantitative analysis due to it only
being found in small quantities and hence its contribution was considered to be insignificant
overall. Teleosts were recorded in 99.8% of the 41 stomachs analyzed and corresponded to a
total of 342 individuals. The striped weakfish C. guatucupa, was the most important teleost (n =
127; %IRI = 49.43) followed by P. porosissimus (n = 90; %IRI = 26.61), and M. furnieri (n = 66;
%IRI = 17.33), whereas the remaining fish species represented less than 6.5 %IRI (Table 2).
Length composition of species eaten ranged from 7 to 24 cm PTL with modal length at 13 cm,
mean 13.18 ± 0.14 cm, and a median of 13 cm PTL (Table 3). The cumulative frequency at 50%
of prey was 13 cm PTL. Fish mean PTL by species eaten were between 11.11 ± 0.22 cm (SD)
and 14.65 ± 0.24 cm (SD) (Table 3). Significant inverse relationships was found between
Fransiscana dolphin total length (FTL) and prey total length (PTL) (cm) (PTL = 14.87 – 0.013
FTL, r = - 0.122; Student t - test = 2.28; p = 0.022 < 0.05), but only 1.5 % of PTL was explained
by FTL (determination coefficient = r^2 = 0,015).


```
The Shannon diversity index was 1.633 (lower (25%) = 1.532, upper (75%) = 1.705), the
evenness index was 0.568 (lower (25%) = 0.514, upper (75%) = 0.611) and the Berger – Parker
index was 0.363 (lower (25%) = 0.315, upper (75%) = 0.415). Levin ́s index standardized of
niche breadth was 0.078 which indicate a specialist feeding strategy of the Franciscana dolphin
in the Uruguayan coast.
```
Table 2. Summary of diet composition of the Franciscana dolphins collected off the Uruguayan
coast.
Prey item Sound FO %FO N %N %W IRI %IRI
Teleosts 93 349
Cynoscion guatucupa Yes 22 23.15 127 36.38 50.78 2018.83 49.43
Porichthys porosissimus Yes 24 25.26 90 25.78 17.23 1087.01 26.61
Micropogonias furnieri Yes 20 21.05 66 18.91 14.71 707.92 17.33
Umbrina canosai Yes 9 9.47 26 7.44 9.51 160.72 3.93
Engraulis anchoita Not 8 8.42 19 5.44 3.94 79.06 1.93
Paralonchurus brasiliensis Not 4 4.21 7 2.00 1.10 13.11 0.32
Macrodon articauda Yes 2 2.10 3 0.85 1.00 3.9 3 0.096
Urophisis brasiliensis Not 4 4.21 4 1.14 0.49 6.89 0.16
Cephalopods 2 7
Loligo sanpaulensis Not 4 2.10 7 2.00 1.18 6.72 0.16
Unidentified species (UI) 8 12


Table 3. Prey size characteristics: size of sample (n), max, min, mean standard error (SE),
variance (s^2 ), standard deviation (SD), median ( , percentiles (PCTL) and coefficient of
variation (CV).
n Min Max Mean SE s^2 SD 25 PCTL 75 PCTL CV
All preys 349 7 24 13.18 0.14 7.05 2.65 13 12 14 20.14
Cynoscion guatucupa 127 11 24 14.65 0.24 7.36 2.71 14.00 13.00 16 18.52
Porichthys porosissimus 90 7 16 11.11 0.22 4.46 2.11 12.00 10.00 12 19.01
Micropogonias furnieri 66 10 21 13.11 0.25 4.07 2.02 13.00 12.00 14 15.38
Umbrina canosai 26 10 16 13.54 0.31 2.58 1.61 13.50 12.00 15 11.86
Engraulis anchoita 19 10 17 12.95 0.40 3.05 1.75 13.00 12. 00 14 13.49
Paralonchurus brasiliensis 7 11 13 12.14 0.34 0.81 0.90 12.00 11.00 13 7.41
Macrodon articauda 7 9 16 12.86 0.86 5.14 2.27 13.00 12.00 15 17.64
Urophisis brasiliensis 3 15 18 16.33 0.88 2.33 1.53 16.00 15.00 18 9.35
Loligo sanpaulensis 4 12 15 13.50 0.65 1.67 1.29 13.50 12.25 14.75 9.56

Discussion
The animals analyzed in this study do not exhibit signs of disease or trauma but most specimens
showed signs of net marks in the skin, including some that were found stranded in the beaches
also had these marks, so probably these dolphins died as a consequence of entanglement in
fishing nets, which is big problem previously described.
The analysis of stomach contents confirms the importance of fish in the diet of the Franciscana
dolphin. The feeding habits along its distribution area is composed by, at least, 76 food items and
the majority of prey belonged to three main zoological groups: fish (82.8%), crustaceans (9.2%),
and molluscs (7.9%) (Fitch & Brownell 1971; Brownell 1975; Pinedo 1982; Brownell 1989;


Bassoi & Secchi 1999; Rodriguez et al., 2002; Bassoi 2005; Paso-Viola et al., 2014). The
number of prey species in this study (nine prey species) is considerably lower compared with
other studies previously performed along its distribution range. In Brazil, a total of 25 prey were
found in dolphins collected north of Rio de Janeiro (Di Beneditto & Ramos 2001), 36 prey
species were identified in a study performed in Rio Grande do Sul (Bassoi 2005), a total of 24
different prey from the northern coast of Buenos Aires (Rodríguez et al., 2002), and finally 11
prey from the southern Buenos Aires coast (Pazo-Viola et al., 2014). Diversity and species
richness indices (Shannon & Berger – Parker, respectively) were low for the Uruguayan coast
and the number of prey species noteworthy low. However, the species reported in this study are
consistent with those found by Fitch & Brownell (1976) and Brownell (1989) from the
Uruguayan coast.
Eight fishes species were found in the stomach in this study, and the preys most
important were C. guatucupa, P. porosissimus and M. furnieri. From this eight fishes species,
five are actively sound producers: M. furnieri (Tellechea et al., 2010, 2011a), C. guatucupa
(Tellechea & Norbis 2012), U. canossai (Tellechea et al., 2 016 ), M. articauda and P.
porosissimus (Tellechea unpublished data). The fishes, particularly those emitting sound, were
the most important Franciscana dolphin food item representing 97.4 % IRI of total prey (Table
2). As reported for southern Brazil and Argentina, Franciscanas in this study prey on juvenile
fish (mean 13.18 ± 0.14) cm and small squids, being the target species C. guatucupa and P.
porosisimus.
In terms of IRI C. guatucupa was the most important prey identified off the Brazilian and
Argentinean coasts together with other sciaenids with smaller IRI as M. furnieri and M.


atricauda (Bassoi & Secchi 1999; Di Beneditto & Ramos 2001; Rodriguez et al., 2002; Bassoi
2005; Paso-Viola et al., 2014). Throughout its distribution area, Franciscana dolphins are
classified as opportunistic in their feeding habits (Rodriguez et al., 2002, Bassoi 2005; Paso-
Viola et al., 2014), however the Levin’s index standardized of niche breadth indicates a specialist
feeding strategy of the Franciscana dolphin population investigated in this study.
It is noteworthy that the toadfish P. porosisimus is second most recurrent prey, and is the
prey with more frequency of occurrence (%25), as previous studies off the Uruguayan coast has
also identified this species as the most consumed prey (Brownell et al., 1989). The P.
porosisimus is still the main difference in the diet of Franciscanas from Uruguay and Argentina,
this species is one of the most important prey item in Uruguay as show this study and past
studies (Praderi 1984; Brownell et al., 1989), but in Argentina is very little recurring (Rodriguez
et al., 2002; Paso-Viola et al., 2014). This fish is hard to find, it inhabits caves in the rocks or
stays buried. This suggests that the Franciscana dolphin may locate this fish in the dark waters of
the Rio de la Plata estuary and the murky waters of the Uruguayan oceanic coast could be
through passive listening.
The hypothesis of using passive listening to find prey is not new, this strategy have been
already described in cetaceans (Barret-Leonard et al., 1996; Barros & Odell 1990; Barros 1993;
Barros & Wells 1998; Gannon et al., 2005; Berens et al., 2010). Passive listening would increase
the capture efficiencies of energetically rich prey (Barros & Wells 1998; Gannon 2005) as many
soniferous fish species raise their frequency and intensity of calls during spawning periods
(Tellechea et al., 2010, 2011a, 2011b; Tellechea & Norbis, 2012). The sounds emitted by fishes
is audible up to 630 m (Gannon 2003) which is much further than the maximum echolocation


detection range known for any other dolphin, regardless of target strength (Au 1993). Given that
fish sounds propagate more or less omnidirectionally (Barimo & Fine 1998), passive listening
would allow dolphins to keep a large area under surveillance without expending energy or
advertising its presence. Therefore, the Franciscana dolphin may obtain useful information from
it, like prey identification and location, body size and number of fish. Using this information to
assess the quality of prey from a distance would surely be advantageous for these predators
(Gannon et al., 2005), once the prey has been detected the Franciscana dolphin could be using
the echolocation to track the prey and capture phases (Au 1993; Gannon et al., 2005; Rigdway et
al., 2015).
Passive listening could contribute to the frequency of Franciscana dolphins ending up as
bycatch as the sound-producing species are the target of some fisheries, possibly causing the
dolphin to approach the artisanal fishing net to feed. These M. furnieri, C. guatucupa, and U.
canosai fish emit disturbance calls when they are tangled in the fisheries nets (Tellechea et al.,
2010, 2011a, Tellechea & Norbis 2012). Bordino et al. (2002) show that even with sonorous
alarms in fishermen nets focused on fishing C. guatucupa, M. furnieri, P. brasiliensis, U.
canosai, all sound producing species, it still caused the Franciscana dolphin to continue to get
entangled in the nets. We therefore suggest that even with the use of acoustic alarms this dolphin
still prefers to go for the easy food in the nets. Franciscana dolphin has been classified as
‘vulnerable’in its whole distribution, principally as a consequence of the incidental mortality in
artisanal fisheries. In consequence, further studies are needed to clarify if this dolphin is attracted
to the fisherman nets by soniferous fish, and to identify ways to successfully prevent them doing
so.
