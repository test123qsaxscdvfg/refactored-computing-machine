{{short description|Restructuring existing computer code without changing its external behavior}}
{{Redirect|Refactoring|its use on Wikipedia|Wikipedia:Refactoring talk pages|selfref = true}}
{{About-distinguish|a behaviour-preserving change|Rewrite (programming)}}

In [[computer programming]] and [[software design]], '''code refactoring''' is the process of restructuring existing [[computer code]]—changing the ''[[decomposition (computer science)|factoring]]''—without changing its external behavior. Refactoring is intended to improve the design, structure, and/or implementation of the [[software]] (its ''[[non-functional requirement|non-functional]]'' attributes), while preserving its [[functional requirement|functionality]]. Potential advantages of refactoring may include improved code [[readability]] and reduced [[cyclomatic complexity|complexity]]; these can improve the [[source code]]{{'}}s [[maintainability]] and create a simpler, cleaner, or more expressive internal [[software architecture|architecture]] or [[object model]] to improve [[extensibility]]. Another potential goal for refactoring is improved performance; software engineers face an ongoing challenge to write programs that perform faster or use less memory.

Typically, refactoring applies a series of standardized basic ''micro-refactorings'', each of which is (usually) a tiny change in a computer program's source code that either preserves the behavior of the software, or at least does not modify its conformance to functional requirements. Many [[Development environment (software development process)|development environments]] provide automated support for performing the mechanical aspects of these basic refactorings. If done well, code refactoring may help software developers discover and fix hidden or dormant [[software bug|bugs]] or [[vulnerability (computing)|vulnerabilities]] in the system by simplifying the underlying logic and eliminating unnecessary levels of complexity. If done poorly, it may fail the requirement that external functionality not be changed, and may thus introduce new bugs.

{{Blockquote|By continuously improving the design of code, we make it easier and easier to work with. This is in sharp contrast to what typically happens: little refactoring and a great deal of attention paid to expediently add new features. If you get into the hygienic habit of refactoring continuously, you'll find that it is easier to extend and maintain code.|Joshua Kerievsky, ''Refactoring to Patterns''<ref name=kerievsky>{{cite book | last = Kerievsky | first = Joshua | title = Refactoring to Patterns | publisher = Addison Wesley | year = 2004  }}</ref>}}

==Motivation==
Refactoring is usually motivated by noticing a [[code smell]].<ref name="fowler"/> For example, the method at hand may be very long, or it may be a near [[duplicate code|duplicate]] of another nearby method. Once recognized, such problems can be addressed by ''refactoring'' the source code, or transforming it into a new form that behaves the same as before but that no longer "smells".

For a long routine, one or more smaller subroutines can be extracted; or for duplicate routines, the duplication can be removed and replaced with one shared function. Failure to perform refactoring can result in accumulating [[technical debt]]; on the other hand, refactoring is one of the primary means of repaying technical debt.<ref>{{cite book|last1=Suryanarayana|first1=Girish|title=Refactoring for Software Design Smells|date=November 2014|publisher=Morgan Kaufmann|isbn=978-0128013977|pages=258}}</ref>

==Benefits==
There are two general categories of benefits to the activity of refactoring.
# [[Maintainability]]. It is easier to fix bugs because the source code is easy to read and the intent of its author is easy to grasp.<ref name=martin>{{cite book | last = Martin | first = Robert |title = Clean Code | publisher = Prentice Hall | year = 2009}}</ref> This might be achieved by reducing large monolithic routines into a set of individually concise, well-named, single-purpose methods. It might be achieved by moving a method to a more appropriate class, or by removing misleading comments.
# [[Extensibility]]. It is easier to extend the capabilities of the application if it uses recognizable [[design pattern (computer science)|design patterns]], and it provides some flexibility where none before may have existed.<ref name=kerievsky/>
Performance engineering can remove inefficiencies in programs, known as software bloat, arising from traditional software-development strategies that aim to minimize an application's development time rather than the time it takes to run. Performance engineering can also tailor [[software]] to the [[Hardware security module|hardware]] on which it runs, for example, to take advantage of parallel processors and vector units.<ref>{{Cite journal|doi=10.1126/science.aam9744|doi-access=free|title=There's plenty of room at the Top: What will drive computer performance after Moore's law?|year=2020|last1=Leiserson|first1=Charles E.|last2=Thompson|first2=Neil C.|last3=Emer|first3=Joel S.|last4=Kuszmaul|first4=Bradley C.|last5=Lampson|first5=Butler W.|last6=Sanchez|first6=Daniel|last7=Schardl|first7=Tao B.|journal=Science|volume=368|issue=6495|pages=eaam9744|pmid=32499413}}</ref>

==Challenges==
Refactoring requires extracting software system structure, data models, and intra-application dependencies to get back knowledge of an existing software system.<ref>
{{Cite book
|last1=Haendler|first1=Thorsten
|last2=Neumann|first2=Gustaf
|title=Proceedings of the 11th International Joint Conference on Knowledge Discovery, Knowledge Engineering and Knowledge Management
|chapter=A Framework for the Assessment and Training of Software Refactoring Competences
|s2cid=204754665
|date=2019
|pages=307–316
|doi=10.5220/0008350803070316
|isbn=978-989-758-382-7
|doi-access=free
}}</ref>
The turnover of teams implies missing or inaccurate knowledge of the current state of a system and about design decisions made by departing developers. Further code refactoring activities may require additional effort to regain this knowledge.<ref>
{{Cite book
|last1=Nassif|first1=Matthieu
|last2=Robillard|first2=Martin P.
|title=2017 IEEE International Conference on Software Maintenance and Evolution (ICSME)
|chapter=Revisiting Turnover-Induced Knowledge Loss in Software Projects
|s2cid=13147063
|date=November 2017
|pages=261–272
|doi=10.1109/ICSME.2017.64
|isbn=978-1-5386-0992-7
}}</ref>
Refactoring activities generate architectural modifications that deteriorate the structural architecture of a software system. Such deterioration affects architectural properties such as maintainability and comprehensibility which can lead to a complete re-development of software systems.
<ref>
{{Cite journal
|last1=van Gurp|first1=Jilles
|last2=Bosch|first2=Jan
|date=March 2002
|title= Design erosion: problems and causes
|journal=Journal of Systems and Software
|volume=61
|issue=2
|pages=105–119
|doi=10.1016/S0164-1212(01)00152-2
}}</ref>

Code refactoring activities are secured with [[software intelligence]] when using tools and techniques providing data about algorithms and  sequences of code execution.<ref>
{{Cite journal
|last1=Hassan|first1=Ahmed E.
|last2=Xie|first2=Tao
|date=November 2010
|title=Software intelligence: the future of mining software engineering data
|journal=In Proceedings of the FSE/SDP Workshop on Future of Software Engineering Research (FoSER '10)
|pages=161–166
|doi=10.1145/1882362.1882397
|s2cid=3485526
}}</ref> Providing a comprehensible format for the inner-state of software system structure, data models, and intra-components dependencies is a critical element to form a high-level understanding and then refined views of what needs to be modified, and how.<ref>
{{Cite journal
|last1=Novais|first1=Renato
|last2=Santos|first2=José Amancio
|last3=Mendonça|first3=Manoel
|date=2017
|title=Experimentally assessing the combination of multiple visualization strategies for software evolution analysis
|journal=Journal of Systems and Software
|volume=128
|pages= 56–71
|doi=10.1016/j.jss.2017.03.006
}}</ref>

==Testing==
Automatic [[unit testing|unit tests]] should be set up before refactoring to ensure routines still behave as expected.<ref>{{Cite book |title=Refactoring : improving the design of existing code |last=Fowler |first=Martin |date=1999 |publisher=Addison-Wesley |isbn=978-0201485677 |location=Reading, MA |oclc=41017370 |url=https://archive.org/details/isbn_9780201485677 }}</ref> Unit tests can bring stability to even large refactors when performed with a single [[Atomic commit#Revision control|atomic commit]]. A common strategy to allow safe and atomic refactors spanning multiple projects is to store all projects in a single [[repository (version control)|repository]], known as [[monorepo]].<ref>{{cite book |last1=Smart |first1=John Ferguson |title=Java Power Tools |date=2008 |publisher="O'Reilly Media, Inc." |isbn=9781491954546 |page=301 |url=https://books.google.com/books?id=kE0UDQAAQBAJ&q=visual+sourcesafe+atomic+commit&pg=PA301 |access-date=26 July 2018 |language=en}}</ref>

With unit testing in place, refactoring is then an iterative cycle of making a small [[program transformation]], testing it to ensure correctness, and making another small transformation. If at any point a test fails, the last small change is undone and repeated in a different way. Through many small steps the program moves from where it was to where you want it to be. For this very iterative process to be practical, the tests must run very quickly, or the programmer would have to spend a large fraction of their time waiting for the tests to finish. Proponents of [[extreme programming]] and other [[agile software development]] describe this activity as an integral part of the [[software development process|software development cycle]].

==Techniques==
Here are some examples of micro-refactorings; some of these may only apply to certain languages or language types. A longer list can be found in [[Martin Fowler (software engineer)|Martin Fowler]]'s refactoring book<ref name="fowler">{{cite book|title=Refactoring. Improving the Design of Existing Code|last=Fowler|first=Martin|publisher=Addison-Wesley|year=1999|isbn=978-0-201-48567-7|pages=[https://archive.org/details/isbn_9780201485677/page/63 63ff]|author-link=Martin Fowler (software engineer)|url=https://archive.org/details/isbn_9780201485677/page/63}}</ref>{{page needed|date=July 2018}} and website.<ref name="refactoring.com">(these are only about OOP however).[http://refactoring.com/catalog/index.html Refactoring techniques in Fowler's refactoring Website]</ref> Many development environments provide automated support for these micro-refactorings. For instance, a programmer could click on the name of a variable and then select the "Encapsulate field" refactoring from a [[context menu]]. The IDE would then prompt for additional details, typically with sensible defaults and a preview of the code changes. After confirmation by the programmer it would carry out the required changes throughout the code.
* Techniques that allow for more [[Application discovery and understanding|understanding]]
** [[Program Dependence Graph]] - explicit representation of data and control dependencies <ref>
{{Cite journal
|last1=Ferrante|first1=Jeanne
|last2=Ottenstein|first2=Karl J.
|last3=Warren|first3=Joe D.
|date=July 1987
|title= The program dependence graph and its use in optimization
|journal=ACM Transactions on Programming Languages and Systems 
|volume=9
|issue=3
|pages=319–349
|publisher=ACM
|doi=10.1145/24039.24041
|s2cid=505075
|doi-access=free
}}</ref>
** System Dependence Graph - representation of procedure calls between PDG <ref>
{{Cite book
|last1=Donglin|first1=Linag
|last2=Harrold|first2=M. J.
|title=Proceedings. International Conference on Software Maintenance (Cat. No. 98CB36272)
|chapter=Slicing objects using system dependence graphs
|date=November 2008
|pages=319–349
|publisher=IEEE
|doi=10.1109/ICSM.1998.738527
|isbn=978-0-8186-8779-2
|s2cid=18160599
}}</ref>
** [[Software intelligence]] - reverse engineers the initial state to understand existing intra-application dependencies
* Techniques that allow for more [[Abstraction (computer science)|abstraction]]
** [[Field encapsulation|Encapsulate field]] – force code to access the field with getter and setter methods
** [[Type generalization|Generalize type]] – create more general types to allow for more code sharing
** Replace type-checking code with state/strategy<ref>{{cite web| url = http://refactoring.com/catalog/replaceTypeCodeWithStateStrategy.html| title = Replace type-checking code with State/Strategy}}</ref>
** Replace conditional with [[Polymorphism (computer science)|polymorphism]]<ref>{{cite web| url = http://refactoring.com/catalog/replaceConditionalWithPolymorphism.html| title = Replace conditional with polymorphism}}</ref>
* Techniques for breaking code apart into more logical pieces
** Componentization breaks code down into reusable semantic units that present clear, well-defined, simple-to-use interfaces.
** [[Extract class]] moves part of the code from an existing class into a new class.
** Extract method, to turn part of a larger [[method (computer science)|method]] into a new method. By breaking down code in smaller pieces, it is more easily understandable. This is also applicable to [[Function (programming)|function]]s.
* Techniques for improving names and location of code
** Move method or move field – move to a more appropriate [[Class (computer science)|class]] or source file
** Rename method or rename field – changing the name into a new one that better reveals its purpose
** Pull up – in [[object-oriented programming]] (OOP), move to a [[Superclass (computer science)|superclass]]
** Push down – in OOP, move to a [[Subclass (computer science)|subclass]]<ref name="refactoring.com"/>
* Automatic [[clone detection]]<ref>Bruntink, Magiel, et al. "[http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.57.9709&rep=rep1&type=pdf An evaluation of clone detection techniques for crosscutting concerns]." Software Maintenance, 2004. Proceedings. 20th IEEE International Conference on. IEEE, 2004.</ref>

==Hardware refactoring==
While the term ''refactoring'' originally referred exclusively to refactoring of software code, in recent years code written in [[hardware description language]]s has also been refactored. The term ''hardware refactoring'' is used as a shorthand term for refactoring of code in hardware description languages. Since hardware description languages are not considered to be [[programming language]]s by most hardware engineers,<ref>[[Hardware description languages#HDL and programming languages]]</ref> hardware refactoring is to be considered a separate field from traditional code refactoring.

Automated refactoring of analog hardware descriptions (in [[VHDL-AMS]]) has been proposed by Zeng and Huss.<ref>Kaiping Zeng, Sorin A. Huss, "Architecture refinements by code refactoring of behavioral VHDL-AMS models". ISCAS 2006</ref> In their approach, refactoring preserves the simulated behavior of a hardware design. The non-functional measurement that improves is that refactored code can be processed by standard synthesis tools, while the original code cannot. Refactoring of digital hardware description languages, albeit manual refactoring, has also been investigated by [[Synopsys]] [[fellow]] Mike Keating.<ref>M. Keating :"Complexity, Abstraction, and the Challenges of Designing Complex Systems", in DAC'08 tutorial [http://www.dac.com/events/eventdetails.aspx?id=77-130] {{Webarchive|url=https://web.archive.org/web/20160328163412/https://dac.com/events/eventdetails.aspx?id=77-130|date=2016-03-28}}"Bridging a Verification Gap: C++ to RTL for Practical Design"</ref><ref>M. Keating, P. Bricaud: ''Reuse Methodology Manual for System-on-a-Chip Designs'', Kluwer Academic Publishers, 1999.</ref> His target is to make complex systems easier to understand, which increases the designers' productivity.

==History==
The first known use of the term "refactoring" in the published literature was in a September, 1990 article by [[William Opdyke]] and [[Ralph Johnson (computer scientist)|Ralph Johnson]].<ref name="opdyke90">{{cite conference
  | first = William F.
  | last = Opdyke
  | author-link = William Opdyke
  |author2=Johnson, Ralph E.
  | title = Refactoring: An Aid in Designing Application Frameworks and Evolving Object-Oriented Systems
  | book-title = Proceedings of the Symposium on Object Oriented Programming Emphasizing Practical Applications (SOOPPA)
  | publisher = ACM
  |date=September 1990
}}</ref>
Griswold's Ph.D. thesis,<ref name="griswold-thesis">{{cite thesis
  | first = William G
  | last = Griswold
  | author-link = Bill Griswold
  | title = Program Restructuring as an Aid to Software Maintenance
  | degree = Ph.D.
  | publisher = University of Washington
  |date=July 1991
  | url = http://cseweb.ucsd.edu/~wgg/Abstracts/gristhesis.pdf
  | access-date = 2011-12-24
}}</ref>
Opdyke's Ph.D. thesis,<ref name="opdyke-thesis">{{cite thesis
  | first = William F
  | last = Opdyke
  | author-link = William Opdyke
  | title = Refactoring Object-Oriented Frameworks
  | degree = Ph.D.
  | publisher = University of Illinois at Urbana-Champaign
  | date = June 1992
  | url = http://dl.acm.org/citation.cfm?id=169783
  | archive-url = https://web.archive.org/web/20191216212919/https://dl.acm.org/citation.cfm?id=169783
  | archive-date = 2019-12-16
  | format = compressed Postscript
  | access-date = 2008-02-12
  | url-status = bot: unknown
  }}</ref> published in 1992, also used this term.<ref name="etymology" /> Although refactoring code has been done informally for decades, [[Bill Griswold|William Griswold]]'s 1991 Ph.D. dissertation<ref name="griswold-thesis" /> is one of the first major academic works on refactoring functional and procedural programs, followed by [[William Opdyke]]'s 1992 dissertation<ref name="opdyke-thesis" /> on the refactoring of object-oriented programs,<ref name="etymology">{{cite web| url = http://martinfowler.com/bliki/EtymologyOfRefactoring.html| title = Martin Fowler, "MF Bliki: EtymologyOfRefactoring"}}</ref> although all the theory and machinery have long been available as [[program transformation]] systems. All of these resources provide a catalog of common methods for refactoring; a refactoring method has a description of how to apply the [[Scientific method|method]] and indicators for when you should (or should not) apply the method.

[[Martin Fowler (software engineer)|Martin Fowler]]'s book ''Refactoring: Improving the Design of Existing Code'' is the canonical reference. {{According to whom|date=July 2018}}

The terms "factoring" and "factoring out" have been used in this way in the [[Forth (programming language)|Forth]] community since at least the early 1980s. Chapter Six of [[Leo Brodie (programmer)|Leo Brodie]]'s book ''[[Thinking Forth]]'' (1984)<ref>{{cite book 
 |last1=Brodie 
 |first1=Leo 
 |title=Thinking Forth 
 |year=2004 
 |isbn=0-9764587-0-5 
 |pages=171–196 
 |publisher=Fig Leaf Press, Forth Interest 
 |url=http://thinking-forth.sourceforge.net 
 |access-date=3 May 2020 
 |archive-url=https://web.archive.org/web/20051216163615/http://thinking-forth.sourceforge.net/ 
 |archive-date=16 December 2005 
 |url-status=dead 
 }}</ref> is dedicated to the subject.

In extreme programming, the Extract Method refactoring technique has essentially the same meaning as factoring in Forth; to break down a "word" (or [[Function (programming)|function]]) into smaller, more easily maintained functions.

Refactorings can also be reconstructed<ref name="What-is-code-refactoring?">{{cite news
  | first = Andriy
  | last = Sokolov
  | title = What is code refactoring?
  | url = https://duecode.io/blog/what-is-code-refactoring/
  }}</ref> posthoc to produce concise descriptions of complex software changes recorded in software repositories like CVS or SVN.

==Automated code refactoring==
{{More citations needed|section|date=July 2018}}
Many software [[text editor|editors]] and [[Integrated development environment|IDEs]] have automated refactoring support.  Here is a list of a few of these editors, or so-called [[Refactoring Browser|refactoring browsers]].
* [[DMS Software Reengineering Toolkit]] (Implements large-scale refactoring for C, C++, C#, COBOL, Java, PHP and other languages)
* Eclipse based:
** [[Eclipse (software)|Eclipse]] (for [[Java (programming language)|Java]], and to a lesser extent, C++, PHP, Ruby and JavaScript)
** [[PyDev]] (for [[Python (programming language)|Python]])
** [[Photran]] (a [[Fortran]] plugin for the [[Eclipse (software)|Eclipse IDE]])
* [[Embarcadero Delphi]]
* IntelliJ based:
** [[Resharper]] (for [[C Sharp (programming language)|C#]])
** [[AppCode]] (for [[Objective-C]], C and C++)
** [[IntelliJ IDEA]] (for [[Java (programming language)|Java]])
** [[PyCharm]] (for [[Python (programming language)|Python]])
** [[WebStorm]] (for [[JavaScript]])
** [[PhpStorm]] (for [[PHP]])
** [[Android Studio]] (for [[Java (programming language)|Java]] and C++)
* [[JDeveloper]] (for [[Java (programming language)|Java]])
* [[NetBeans]] (for [[Java (programming language)|Java]])
*[[Smalltalk]]: Most dialects include powerful refactoring tools. Many use the original refactoring browser produced in the early '90s by [[Ralph Johnson (computer scientist)|Ralph Johnson]].
* Visual Studio based:
** [[Visual Studio]] (for .NET and C++)
** [[CodeRush]] (addon for Visual Studio)
** [[Visual Assist]] (addon for Visual Studio with refactoring support for C# and C++)
* [[Wing IDE]] (for [[Python (programming language)|Python]])
* [[Xcode]] (for C, [[Objective-C]], and [[Swift (programming language)|Swift]])<ref>{{cite web| url = https://developer.apple.com/library/content/documentation/DeveloperTools/Conceptual/WhatsNewXcode/xcode_9/xcode_9.html| title = What's new in Xcode 9}}</ref>
* [[Qt Creator]] (for C++, Objective-C and QML)<ref>{{cite web| url = https://doc.qt.io/qtcreator/creator-editor-refactoring.html| title = Refactoring in Qt Creator}}</ref>

==See also==
* [[Amelioration pattern]]
* [[Code review]]
* [[Database refactoring]]
* [[Decomposition (computer science)]]
* [[Modular programming]]
* [[Obfuscated code]]
* [[Prefactoring]]
* [[Rewrite (programming)]]
* [[Separation of concerns]]
* [[Software peer review]]
* [[Test-driven development]]

==References==
{{Reflist}}

==Further reading==
*{{cite book
 | first = William C.
 | last = Wake
 | year = 2003
 | title = Refactoring Workbook
 | publisher = Addison-Wesley
 | isbn = 978-0-321-10929-3
}}
* {{cite journal|first1=T.|last1=Mens|first2=T.|last2=Tourwe|title=A survey of software refactoring|url=https://zenodo.org/record/848931|journal=IEEE Transactions on Software Engineering|date=February 2004|issn=0098-5589|pages=126–139|volume=30|issue=2|doi=10.1109/tse.2004.1265817|s2cid=206778272}}
*{{cite book
 | first = Michael C
 | last = Feathers
 | year = 2004
 | title = Working Effectively with Legacy Code
 | publisher = Prentice Hall
 | isbn = 978-0-13-117705-5
}}
*{{cite book
 | first = Joshua
 | last = Kerievsky
 | year = 2004
 | title = Refactoring To Patterns
 | publisher = Addison-Wesley
 | isbn = 978-0-321-21335-8
}}
*{{cite book
 | first = Danijel
 | last = Arsenovski
 | year = 2008
 | title = Professional Refactoring in Visual Basic
 | publisher = Wrox
 | isbn = 978-0-470-17979-6
}}
*{{cite book
 | first = Danijel
 | last = Arsenovski
 | year = 2009
 | title = Professional Refactoring in C# and ASP.NET
 | publisher = Wrox
 | isbn = 978-0-470-43452-9
}}
*{{cite book
 | first = Peter
 | last = Ritchie
 | year = 2010
 | title = Refactoring with Visual Studio 2010
 | publisher = Packt
 | isbn = 978-1-84968-010-3
}}

==External links==
*[http://c2.com/cgi/wiki?WhatIsRefactoring What Is Refactoring?] (c2.com article)
*[http://refactoring.com/ Martin Fowler's homepage about refactoring]
*{{curlie|Computers/Programming/Methodologies/Refactoring|Refactoring}}

{{Authority control}}

[[Category:Code refactoring| ]]
[[Category:Extreme programming]]
[[Category:Technology neologisms]]
