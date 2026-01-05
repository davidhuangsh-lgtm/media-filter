# Media Filter (信息鉴别助手)

A mobile application designed to help the elderly identify fake news and misleading information online.

## Project Structure

```
media_filter/
├── backend/          # Python FastAPI Backend
│   ├── main.py       # API Service
│   ├── requirements.txt
│   └── .env.example
├── ios/              # Primary iOS App (Kotlin Multiplatform + SwiftUI)
│   ├── composeApp/   # Shared Kotlin logic
│   └── iosApp/       # SwiftUI app + Share Extension
└── web/              # Web App (Expo)
    ├── app/          # Application Pages (Router)
    └── lib/          # Utilities & API client
```

## Quick Start

### 1. Start Backend

```bash
cd backend

# Create virtual environment
python3 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Configure API Key
cp .env.example .env
# Edit .env and fill in your DEEPSEEK_API_KEY
# Note: Currently uses DeepSeek API (OpenAI compatible)

# Start service
python main.py
```

The backend will run at http://localhost:8000

### 2. Run iOS App

```bash
cd ios
./gradlew :composeApp:linkDebugFrameworkIosSimulatorArm64
```

Then open `ios/iosApp/iosApp.xcodeproj` in Xcode and run.

**Note**: For physical device testing, update `baseUrl` in `ios/composeApp/src/commonMain/kotlin/.../network/MediaFilterApi.kt` to your Mac's LAN IP.

### 3. Run Web App

```bash
cd web
npm install
npm run web
```

The web app will run at http://localhost:8081

## Features

- [x] WeChat Official Account article link analysis
- [x] Direct text input analysis
- [x] Credibility assessment (Reliable / Caution / Misleading)
- [x] Detailed analysis explanations
- [x] iOS Share Extension (share directly from Safari/WeChat)
- [x] Dark/Light theme support
- [ ] Douyin video analysis (Planned)
- [ ] WeChat Video Channel analysis (Planned)

## Tech Stack

- **Backend**: Python, FastAPI, BeautifulSoup, DeepSeek API
- **iOS**: Kotlin Multiplatform, SwiftUI, Ktor
- **Web**: React Native (Expo), TypeScript

## Computerization

Developed by the **Computerization** club, **with the assistance of deep neural networks** (to learn more, see [AI Lab](https://github.com/WFLA-AI-Lab)). We are dedicated to helping the community through technology.

PEP 0 – Index of Python Enhancement Proposals (PEPs)
Author:
The PEP Editors
Status:
Active
Type:
Informational
Created:
13-Jul-2000
Table of Contents
Introduction
This PEP contains the index of all Python Enhancement Proposals, known as PEPs. PEP numbers are assigned by the PEP editors, and once assigned are never changed. The version control history of the PEP texts represent their historical record.

Topics
PEPs for specialist subjects are indexed by topic.

Governance PEPs
Packaging PEPs
Release PEPs
Typing PEPs
API
The PEPS API is a JSON file of metadata about all the published PEPs. Read more here.

Numerical Index
The numerical index contains a table of all PEPs, ordered by number.

Index by Category
Process and Meta-PEPs
PEP	Title	Authors	
PA	1	PEP Purpose and Guidelines	Barry Warsaw, Jeremy Hylton, David Goodger, Alyssa Coghlan	
PA	2	Procedure for Adding New Modules	Brett Cannon, Martijn Faassen	
PA	4	Deprecation of Standard Modules	Brett Cannon, Martin von Löwis	
PA	7	Style Guide for C Code	Guido van Rossum, Barry Warsaw	
PA	8	Style Guide for Python Code	Guido van Rossum, Barry Warsaw, Alyssa Coghlan	
PA	10	Voting Guidelines	Barry Warsaw	
PA	11	CPython platform support	Martin von Löwis, Brett Cannon	
PA	12	Sample reStructuredText PEP Template	David Goodger, Barry Warsaw, Brett Cannon	
PA	13	Python Language Governance	The Python core team and community	
PA	387	Backwards Compatibility Policy	Benjamin Peterson	
PA	545	Python Documentation Translations	Julien Palard, Inada Naoki, Victor Stinner	
PA	602	Annual Release Cycle for Python	Łukasz Langa	3.9
PA	609	Python Packaging Authority (PyPA) Governance	Dustin Ingram, Pradyun Gedam, Sumana Harihareswara	
PA	676	PEP Infrastructure Process	Adam Turner	
PA	729	Typing governance process	Jelle Zijlstra, Shantanu Jain	
PA	731	C API Working Group Charter	Guido van Rossum, Petr Viktorin, Victor Stinner, Steve Dower, Irit Katriel	
PA	732	The Python Documentation Editorial Board	Joanna Jablonski	
PA	761	Deprecating PGP signatures for CPython artifacts	Seth Michael Larson	3.14
PA	811	Defining Python Security Response Team membership and responsibilities	Seth Michael Larson	
Other Informational PEPs
PEP	Title	Authors	
IA	20	The Zen of Python	Tim Peters	
IA	101	Doing Python Releases 101	Barry Warsaw, Guido van Rossum	
IF	247	API for Cryptographic Hash Functions	A.M. Kuchling	
IF	248	Python Database API Specification v1.0	Greg Stein, Marc-André Lemburg	
IF	249	Python Database API Specification v2.0	Marc-André Lemburg	
IA	257	Docstring Conventions	David Goodger, Guido van Rossum	
IF	272	API for Block Encryption Algorithms v1.0	A.M. Kuchling	
IA	287	reStructuredText Docstring Format	David Goodger	
IA	290	Code Migration and Modernization	Raymond Hettinger	
IF	333	Python Web Server Gateway Interface v1.0	Phillip J. Eby	
IA	394	The “python” Command on Unix-Like Systems	Kerrick Staley, Alyssa Coghlan, Barry Warsaw, Petr Viktorin, Miro Hrončok, Carol Willing	
IF	399	Pure Python/C Accelerator Module Compatibility Requirements	Brett Cannon	3.3
IF	430	Migrating to Python 3 as the default online documentation	Alyssa Coghlan	
IA	434	IDLE Enhancement Exception for All Branches	Todd Rovito, Terry Reedy	
IF	452	API for Cryptographic Hash Functions v2.0	A.M. Kuchling, Christian Heimes	
IF	457	Notation For Positional-Only Parameters	Larry Hastings	
IF	482	Literature Overview for Type Hints	Łukasz Langa	
IF	483	The Theory of Type Hints	Guido van Rossum, Ivan Levkivskyi	
IA	514	Python registration in the Windows registry	Steve Dower	
IF	579	Refactoring C functions and methods	Jeroen Demeyer	
IF	588	GitHub Issues Migration Plan	Mariatta	
IF	607	Reducing CPython’s Feature Delivery Latency	Łukasz Langa, Steve Dower, Alyssa Coghlan	3.9
IA	619	Python 3.10 Release Schedule	Pablo Galindo Salgado	3.10
IF	630	Isolating Extension Modules	Petr Viktorin	
IF	635	Structural Pattern Matching: Motivation and Rationale	Tobias Kohn, Guido van Rossum	3.10
IF	636	Structural Pattern Matching: Tutorial	Daniel F Moisset	3.10
IF	659	Specializing Adaptive Interpreter	Mark Shannon	
IA	664	Python 3.11 Release Schedule	Pablo Galindo Salgado	3.11
IA	672	Unicode-related Security Considerations for Python	Petr Viktorin	
IA	693	Python 3.12 Release Schedule	Thomas Wouters	3.12
IA	719	Python 3.13 Release Schedule	Thomas Wouters	3.13
IF	733	An Evaluation of Python’s Public C API	Erlend Egeberg Aasland, Domenico Andreoli, Stefan Behnel, Carl Friedrich Bolz-Tereick, Simon Cross, Steve Dower, Tim Felgentreff, David Hewitt, Shantanu Jain, Wenzel Jakob, Irit Katriel, Marc-Andre Lemburg, Donghee Na, Karl Nelson, Ronald Oussoren, Antoine Pitrou, Neil Schemenauer, Mark Shannon, Stepan Sindelar, Gregory P. Smith, Eric Snow, Victor Stinner, Guido van Rossum, Petr Viktorin, Carol Willing, William Woodruff, David Woods, Jelle Zijlstra	
IA	745	Python 3.14 Release Schedule	Hugo van Kemenade	3.14
IF	762	REPL-acing the default REPL	Pablo Galindo Salgado, Łukasz Langa, Lysandros Nikolaou, Emily Morehouse-Valcarcel	3.13
IA	790	Python 3.15 Release Schedule	Hugo van Kemenade	3.15
IA	801	Reserved	Barry Warsaw	
IF	3333	Python Web Server Gateway Interface v1.0.1	Phillip J. Eby	
IF	8000	Python Language Governance Proposal Overview	Barry Warsaw	
IF	8002	Open Source Governance Survey	Barry Warsaw, Łukasz Langa, Antoine Pitrou, Doug Hellmann, Carol Willing	
IA	8016	The Steering Council Model	Nathaniel J. Smith, Donald Stufft	
IF	8100	January 2019 Steering Council election	Nathaniel J. Smith, Ee Durbin	
IF	8101	2020 Term Steering Council election	Ewa Jodlowska, Ee Durbin	
IF	8102	2021 Term Steering Council election	Ewa Jodlowska, Ee Durbin, Joe Carey	
IF	8103	2022 Term Steering Council election	Ewa Jodlowska, Ee Durbin, Joe Carey	
IF	8104	2023 Term Steering Council election	Ee Durbin	
IF	8105	2024 Term Steering Council election	Ee Durbin	
IF	8106	2025 Term Steering Council election	Ee Durbin	
IF	8107	2026 Term Steering Council election	Ee Durbin	
Provisional PEPs (provisionally accepted; interface may still change)
PEP	Title	Authors
SP	708	Extending the Repository API to Mitigate Dependency Confusion Attacks	Donald Stufft
Accepted PEPs (accepted; may not be implemented yet)
PEP	Title	Authors	
SA	458	Secure PyPI downloads with signed repository metadata	Trishank Karthik Kuppusamy, Vladimir Diaz, Marina Moore, Lukas Puehringer, Joshua Lock, Lois Anne DeLong, Justin Cappos	
SA	658	Serve Distribution Metadata in the Simple Repository API	Tzu-ping Chung	
SA	668	Marking Python base environments as “externally managed”	Geoffrey Thomas, Matthias Klose, Filipe Laíns, Donald Stufft, Tzu-ping Chung, Stefano Rivera, Elana Hashman, Pradyun Gedam	
SA	686	Make UTF-8 mode default	Inada Naoki	3.15
SA	687	Isolating modules in the standard library	Erlend Egeberg Aasland, Petr Viktorin	3.12
SA	691	JSON-based Simple API for Python Package Indexes	Donald Stufft, Pradyun Gedam, Cooper Lees, Dustin Ingram	
SA	699	Remove private dict version field added in PEP 509	Ken Jin	3.12
SA	701	Syntactic formalization of f-strings	Pablo Galindo Salgado, Batuhan Taskaya, Lysandros Nikolaou, Marta Gómez Macías	3.12
SA	703	Making the Global Interpreter Lock Optional in CPython	Sam Gross	3.13
SA	714	Rename dist-info-metadata in the Simple API	Donald Stufft	
SA	728	TypedDict with Typed Extra Items	Zixuan James Li	3.15
SA	739	build-details.json 1.0 — a static description file for Python build details	Filipe Laíns	3.14
SA	753	Uniform project URLs in core metadata	William Woodruff, Facundo Tuesca	
SA	770	Improving measurability of Python packages with Software Bill-of-Materials	Seth Larson	
SA	773	A Python Installation Manager for Windows	Steve Dower	
SA	793	PyModExport: A new entry point for C extension modules	Petr Viktorin	3.15
SA	794	Import Name Metadata	Brett Cannon	
SA	798	Unpacking in Comprehensions	Adam Hartz, Erik Demaine	3.15
SA	799	A dedicated profiling package for organizing Python profiling tools	Pablo Galindo Salgado, László Kiss Kollár	3.15
SA	810	Explicit lazy imports	Pablo Galindo Salgado, Germán Méndez Bravo, Thomas Wouters, Dino Viehland, Brittany Reynoso, Noah Kim, Tim Stumbaugh	3.15
Open PEPs (under consideration)
PEP	Title	Authors	
S	467	Minor API improvements for binary sequences	Alyssa Coghlan, Ethan Furman	3.15
S	480	Surviving a Compromise of PyPI: End-to-end signing of packages	Trishank Karthik Kuppusamy, Vladimir Diaz, Justin Cappos, Marina Moore	
S	603	Adding a frozenmap type to collections	Yury Selivanov	
S	638	Syntactic Macros	Mark Shannon	
S	653	Precise Semantics for Pattern Matching	Mark Shannon	
S	671	Syntax for late-bound function argument defaults	Chris Angelico	3.12
S	694	Upload 2.0 API for Python Package Indexes	Barry Warsaw, Donald Stufft, Ee Durbin	
S	710	Recording the provenance of installed packages	Fridolín Pokorný	
S	711	PyBI: a standard format for distributing Python Binaries	Nathaniel J. Smith	
S	718	Subscriptable functions	James Hilton-Balfe	3.15
I	720	Cross-compiling Python packages	Filipe Laíns	3.12
S	725	Specifying external dependencies in pyproject.toml	Pradyun Gedam, Jaime Rodríguez-Guerra, Ralf Gommers	
S	743	Add Py_OMIT_LEGACY_API to the Python C API	Victor Stinner, Petr Viktorin	3.15
I	744	JIT Compilation	Brandt Bucher, Savannah Ostrowski	3.13
S	746	Type checking Annotated metadata	Adrian Garcia Badaracco	3.15
S	747	Annotating Type Forms	David Foster, Eric Traut	3.15
S	748	A Unified TLS API for Python	Joop van de Pol, William Woodruff	3.14
S	752	Implicit namespaces for package repositories	Ofek Lev, Jarek Potiuk	
P	755	Implicit namespace policy for PyPI	Ofek Lev	
S	764	Inline typed dictionaries	Victorien Plot	3.15
I	766	Explicit Priority Choices Among Multiple Indexes	Michael Sarahan	
S	767	Annotating Read-Only Attributes	Eneg	3.15
S	771	Default Extras for Python Software Packages	Thomas Robitaille, Jonathan Dekhtiar	
P	772	Packaging Council governance process	Barry Warsaw, Deb Nicholson, Pradyun Gedam	
I	776	Emscripten Support	Hood Chatham	3.14
S	777	How to Re-invent the Wheel	Emma Harper Smith	
S	780	ABI features as environment markers	Klaus Zimmermann, Ralf Gommers	3.14
S	781	Make TYPE_CHECKING a built-in constant	Inada Naoki	3.15
S	783	Emscripten Packaging	Hood Chatham	
S	785	New methods for easier handling of ExceptionGroups	Zac Hatfield-Dodds	3.14
S	788	Protecting the C API from Interpreter Finalization	Peter Bierma	3.15
S	789	Preventing task-cancellation bugs by limiting yield in async generators	Zac Hatfield-Dodds, Nathaniel J. Smith	3.14
S	800	Disjoint bases in the type system	Jelle Zijlstra	3.15
S	802	Display Syntax for the Empty Set	Adam Turner	3.15
S	803	Stable ABI for Free-Threaded Builds	Petr Viktorin	3.15
S	804	An external dependency registry and name mapping mechanism	Pradyun Gedam, Ralf Gommers, Michał Górny, Jaime Rodríguez-Guerra, Michael Sarahan	
S	806	Mixed sync/async context managers with precise async marking	Zac Hatfield-Dodds	3.15
S	807	Index support for Trusted Publishing	William Woodruff	
S	808	Including static values in dynamic project metadata	Henry Schreiner, Cristian Le	
S	809	Stable ABI for the Future	Steve Dower	3.15
S	814	Add frozendict built-in type	Victor Stinner, Donghee Na	3.15
S	815	Deprecate RECORD.jws and RECORD.p7s	Konstantin Schütze, William Woodruff	
I	816	WASI Support	Brett Cannon	
Finished PEPs (done, with a stable interface)
PEP	Title	Authors	
SF	100	Python Unicode Integration	Marc-André Lemburg	2.0
SF	201	Lockstep Iteration	Barry Warsaw	2.0
SF	202	List Comprehensions	Barry Warsaw	2.0
SF	203	Augmented Assignments	Thomas Wouters	2.0
SF	205	Weak References	Fred L. Drake, Jr.	2.1
SF	207	Rich Comparisons	Guido van Rossum, David Ascher	2.1
SF	208	Reworking the Coercion Model	Neil Schemenauer, Marc-André Lemburg	2.1
SF	214	Extended Print Statement	Barry Warsaw	2.0
SF	217	Display Hook for Interactive Use	Moshe Zadka	2.1
SF	218	Adding a Built-In Set Object Type	Greg Wilson, Raymond Hettinger	2.2
SF	221	Import As	Thomas Wouters	2.0
SF	223	Change the Meaning of x Escapes	Tim Peters	2.0
SF	227	Statically Nested Scopes	Jeremy Hylton	2.1
SF	229	Using Distutils to Build Python	A.M. Kuchling	2.1
SF	230	Warning Framework	Guido van Rossum	2.1
SF	232	Function Attributes	Barry Warsaw	2.1
SF	234	Iterators	Ka-Ping Yee, Guido van Rossum	2.1
SF	235	Import on Case-Insensitive Platforms	Tim Peters	2.1
SF	236	Back to the __future__	Tim Peters	2.1
SF	237	Unifying Long Integers and Integers	Moshe Zadka, Guido van Rossum	2.2
SF	238	Changing the Division Operator	Moshe Zadka, Guido van Rossum	2.2
SF	250	Using site-packages on Windows	Paul Moore	2.2
SF	252	Making Types Look More Like Classes	Guido van Rossum	2.2
SF	253	Subtyping Built-in Types	Guido van Rossum	2.2
SF	255	Simple Generators	Neil Schemenauer, Tim Peters, Magnus Lie Hetland	2.2
SF	260	Simplify xrange()	Guido van Rossum	2.2
SF	261	Support for “wide” Unicode characters	Paul Prescod	2.2
SF	263	Defining Python Source Code Encodings	Marc-André Lemburg, Martin von Löwis	2.3
SF	264	Future statements in simulated shells	Michael Hudson	2.2
SF	273	Import Modules from Zip Archives	James C. Ahlstrom	2.3
SF	274	Dict Comprehensions	Barry Warsaw	2.7, 3.0
SF	277	Unicode file name support for Windows NT	Neil Hodgson	2.3
SF	278	Universal Newline Support	Jack Jansen	2.3
SF	279	The enumerate() built-in function	Raymond Hettinger	2.3
SF	282	A Logging System	Vinay Sajip, Trent Mick	2.3
SF	285	Adding a bool type	Guido van Rossum	2.3
SF	289	Generator Expressions	Raymond Hettinger	2.4
SF	292	Simpler String Substitutions	Barry Warsaw	2.4
SF	293	Codec Error Handling Callbacks	Walter Dörwald	2.3
SF	301	Package Index and Metadata for Distutils	Richard Jones	2.3
SF	302	New Import Hooks	Just van Rossum, Paul Moore	2.3
SF	305	CSV File API	Kevin Altis, Dave Cole, Andrew McNamara, Skip Montanaro, Cliff Wells	2.3
SF	307	Extensions to the pickle protocol	Guido van Rossum, Tim Peters	2.3
SF	308	Conditional Expressions	Guido van Rossum, Raymond Hettinger	2.5
SF	309	Partial Function Application	Peter Harris	2.5
SF	311	Simplified Global Interpreter Lock Acquisition for Extensions	Mark Hammond	2.3
SF	318	Decorators for Functions and Methods	Kevin D. Smith, Jim J. Jewett, Skip Montanaro, Anthony Baxter	2.4
SF	322	Reverse Iteration	Raymond Hettinger	2.4
SF	324	subprocess - New process module	Peter Astrand	2.4
SF	327	Decimal Data Type	Facundo Batista	2.4
SF	328	Imports: Multi-Line and Absolute/Relative	Aahz	2.4, 2.5, 2.6
SF	331	Locale-Independent Float/String Conversions	Christian R. Reis	2.4
SF	338	Executing modules as scripts	Alyssa Coghlan	2.5
SF	341	Unifying try-except and try-finally	Georg Brandl	2.5
SF	342	Coroutines via Enhanced Generators	Guido van Rossum, Phillip J. Eby	2.5
SF	343	The “with” Statement	Guido van Rossum, Alyssa Coghlan	2.5
SF	352	Required Superclass for Exceptions	Brett Cannon, Guido van Rossum	2.5
SF	353	Using ssize_t as the index type	Martin von Löwis	2.5
SF	357	Allowing Any Object to be Used for Slicing	Travis Oliphant	2.5
SF	358	The “bytes” Object	Neil Schemenauer, Guido van Rossum	2.6, 3.0
SF	362	Function Signature Object	Brett Cannon, Jiwon Seo, Yury Selivanov, Larry Hastings	3.3
SF	366	Main module explicit relative imports	Alyssa Coghlan	2.6, 3.0
SF	370	Per user site-packages directory	Christian Heimes	2.6, 3.0
SF	371	Addition of the multiprocessing package to the standard library	Jesse Noller, Richard Oudkerk	2.6, 3.0
SF	372	Adding an ordered dictionary to collections	Armin Ronacher, Raymond Hettinger	2.7, 3.1
SF	376	Database of Installed Python Distributions	Tarek Ziadé	2.7, 3.2
SF	378	Format Specifier for Thousands Separator	Raymond Hettinger	2.7, 3.1
SF	380	Syntax for Delegating to a Subgenerator	Gregory Ewing	3.3
SF	383	Non-decodable Bytes in System Character Interfaces	Martin von Löwis	3.1
SF	384	Defining a Stable ABI	Martin von Löwis	3.2
SF	389	argparse - New Command Line Parsing Module	Steven Bethard	2.7, 3.2
SF	391	Dictionary-Based Configuration For Logging	Vinay Sajip	2.7, 3.2
SF	393	Flexible String Representation	Martin von Löwis	3.3
SF	397	Python launcher for Windows	Mark Hammond, Martin von Löwis	3.3
SF	405	Python Virtual Environments	Carl Meyer	3.3
SF	409	Suppressing exception context	Ethan Furman	3.3
SF	412	Key-Sharing Dictionary	Mark Shannon	3.3
SF	414	Explicit Unicode Literal for Python 3.3	Armin Ronacher, Alyssa Coghlan	3.3
SF	415	Implement context suppression with exception attributes	Benjamin Peterson	3.3
SF	417	Including mock in the Standard Library	Michael Foord	3.3
SF	418	Add monotonic time, performance counter, and process time functions	Cameron Simpson, Jim J. Jewett, Stephen J. Turnbull, Victor Stinner	3.3
SF	420	Implicit Namespace Packages	Eric V. Smith	3.3
SF	421	Adding sys.implementation	Eric Snow	3.3
SF	424	A method for exposing a length hint	Alex Gaynor	3.4
SF	425	Compatibility Tags for Built Distributions	Daniel Holth	3.4
SF	427	The Wheel Binary Package Format 1.0	Daniel Holth	
SF	428	The pathlib module – object-oriented filesystem paths	Antoine Pitrou	3.4
SF	435	Adding an Enum type to the Python standard library	Barry Warsaw, Eli Bendersky, Ethan Furman	3.4
SF	436	The Argument Clinic DSL	Larry Hastings	3.4
SF	440	Version Identification and Dependency Specification	Alyssa Coghlan, Donald Stufft	
SF	441	Improving Python ZIP Application Support	Daniel Holth, Paul Moore	3.5
SF	442	Safe object finalization	Antoine Pitrou	3.4
SF	443	Single-dispatch generic functions	Łukasz Langa	3.4
SF	445	Add new APIs to customize Python memory allocators	Victor Stinner	3.4
SF	446	Make newly created file descriptors non-inheritable	Victor Stinner	3.4
SF	448	Additional Unpacking Generalizations	Joshua Landau	3.5
SF	450	Adding A Statistics Module To The Standard Library	Steven D’Aprano	3.4
SF	451	A ModuleSpec Type for the Import System	Eric Snow	3.4
SF	453	Explicit bootstrapping of pip in Python installations	Donald Stufft, Alyssa Coghlan	
SF	454	Add a new tracemalloc module to trace Python memory allocations	Victor Stinner	3.4
SF	456	Secure and interchangeable hash algorithm	Christian Heimes	3.4
SF	461	Adding % formatting to bytes and bytearray	Ethan Furman	3.5
SF	465	A dedicated infix operator for matrix multiplication	Nathaniel J. Smith	3.5
SF	466	Network Security Enhancements for Python 2.7.x	Alyssa Coghlan	2.7.9
SF	468	Preserving the order of **kwargs in a function.	Eric Snow	3.6
SF	471	os.scandir() function – a better and faster directory iterator	Ben Hoyt	3.5
SF	475	Retry system calls failing with EINTR	Charles-François Natali, Victor Stinner	3.5
SF	476	Enabling certificate verification by default for stdlib http clients	Alex Gaynor	2.7.9, 3.4.3, 3.5
SF	477	Backport ensurepip (PEP 453) to Python 2.7	Donald Stufft, Alyssa Coghlan	
SF	479	Change StopIteration handling inside generators	Chris Angelico, Guido van Rossum	3.5
SF	484	Type Hints	Guido van Rossum, Jukka Lehtosalo, Łukasz Langa	3.5
SF	485	A Function for testing approximate equality	Christopher Barker	3.5
SF	486	Make the Python Launcher aware of virtual environments	Paul Moore	3.5
SF	487	Simpler customisation of class creation	Martin Teichmann	3.6
SF	488	Elimination of PYO files	Brett Cannon	3.5
SF	489	Multi-phase extension module initialization	Petr Viktorin, Stefan Behnel, Alyssa Coghlan	3.5
SF	492	Coroutines with async and await syntax	Yury Selivanov	3.5
SF	493	HTTPS verification migration tools for Python 2.7	Alyssa Coghlan, Robert Kuska, Marc-André Lemburg	2.7.12
SF	495	Local Time Disambiguation	Alexander Belopolsky, Tim Peters	3.6
SF	498	Literal String Interpolation	Eric V. Smith	3.6
SF	503	Simple Repository API	Donald Stufft	
SF	506	Adding A Secrets Module To The Standard Library	Steven D’Aprano	3.6
SF	508	Dependency specification for Python Software Packages	Robert Collins	
SF	515	Underscores in Numeric Literals	Georg Brandl, Serhiy Storchaka	3.6
SF	517	A build-system independent format for source trees	Nathaniel J. Smith, Thomas Kluyver	
SF	518	Specifying Minimum Build System Requirements for Python Projects	Brett Cannon, Nathaniel J. Smith, Donald Stufft	
SF	519	Adding a file system path protocol	Brett Cannon, Koos Zevenhoven	3.6
SF	520	Preserving Class Attribute Definition Order	Eric Snow	3.6
SF	523	Adding a frame evaluation API to CPython	Brett Cannon, Dino Viehland	3.6
SF	524	Make os.urandom() blocking on Linux	Victor Stinner	3.6
SF	525	Asynchronous Generators	Yury Selivanov	3.6
SF	526	Syntax for Variable Annotations	Ryan Gonzalez, Philip House, Ivan Levkivskyi, Lisa Roach, Guido van Rossum	3.6
SF	527	Removing Un(der)used file types/extensions on PyPI	Donald Stufft	
SF	528	Change Windows console encoding to UTF-8	Steve Dower	3.6
SF	529	Change Windows filesystem encoding to UTF-8	Steve Dower	3.6
SF	530	Asynchronous Comprehensions	Yury Selivanov	3.6
SF	538	Coercing the legacy C locale to a UTF-8 based locale	Alyssa Coghlan	3.7
SF	539	A New C-API for Thread-Local Storage in CPython	Erik M. Bray, Masayuki Yamamoto	3.7
SF	540	Add a new UTF-8 Mode	Victor Stinner	3.7
SF	544	Protocols: Structural subtyping (static duck typing)	Ivan Levkivskyi, Jukka Lehtosalo, Łukasz Langa	3.8
SF	552	Deterministic pycs	Benjamin Peterson	3.7
SF	553	Built-in breakpoint()	Barry Warsaw	3.7
SF	557	Data Classes	Eric V. Smith	3.7
SF	560	Core support for typing module and generic types	Ivan Levkivskyi	3.7
SF	561	Distributing and Packaging Type Information	Emma Harper Smith	3.7
SF	562	Module __getattr__ and __dir__	Ivan Levkivskyi	3.7
SF	564	Add new time functions with nanosecond resolution	Victor Stinner	3.7
SF	565	Show DeprecationWarning in __main__	Alyssa Coghlan	3.7
SF	566	Metadata for Python Software Packages 2.1	Dustin Ingram	3.x
SF	567	Context Variables	Yury Selivanov	3.7
SF	570	Python Positional-Only Parameters	Larry Hastings, Pablo Galindo Salgado, Mario Corchero, Eric N. Vander Weele	3.8
SF	572	Assignment Expressions	Chris Angelico, Tim Peters, Guido van Rossum	3.8
SF	573	Module State Access from C Extension Methods	Petr Viktorin, Alyssa Coghlan, Eric Snow, Marcel Plch	3.9
SF	574	Pickle protocol 5 with out-of-band data	Antoine Pitrou	3.8
SF	578	Python Runtime Audit Hooks	Steve Dower	3.8
SF	584	Add Union Operators To dict	Steven D’Aprano, Brandt Bucher	3.9
SF	585	Type Hinting Generics In Standard Collections	Łukasz Langa	3.9
SF	586	Literal Types	Michael Lee, Ivan Levkivskyi, Jukka Lehtosalo	3.8
SF	587	Python Initialization Configuration	Victor Stinner, Alyssa Coghlan	3.8
SF	589	TypedDict: Type Hints for Dictionaries with a Fixed Set of Keys	Jukka Lehtosalo	3.8
SF	590	Vectorcall: a fast calling protocol for CPython	Mark Shannon, Jeroen Demeyer	3.8
SF	591	Adding a final qualifier to typing	Michael J. Sullivan, Ivan Levkivskyi	3.8
SF	592	Adding “Yank” Support to the Simple API	Donald Stufft	
SF	593	Flexible function and variable annotations	Till Varoquaux, Konstantin Kashin	3.9
SF	594	Removing dead batteries from the standard library	Christian Heimes, Brett Cannon	3.11
SF	597	Add optional EncodingWarning	Inada Naoki	3.10
SF	600	Future ‘manylinux’ Platform Tags for Portable Linux Built Distributions	Nathaniel J. Smith, Thomas Kluyver	
SF	604	Allow writing union types as X | Y	Philippe PRADOS, Maggie Moss	3.10
SF	610	Recording the Direct URL Origin of installed distributions	Stéphane Bidoul, Chris Jerdonek	
SF	612	Parameter Specification Variables	Mark Mendoza	3.10
SF	613	Explicit Type Aliases	Shannon Zhu	3.10
SF	614	Relaxing Grammar Restrictions On Decorators	Brandt Bucher	3.9
SF	615	Support for the IANA Time Zone Database in the Standard Library	Paul Ganssle	3.9
SF	616	String methods to remove prefixes and suffixes	Dennis Sweeney	3.9
SF	617	New PEG parser for CPython	Guido van Rossum, Pablo Galindo Salgado, Lysandros Nikolaou	3.9
SF	618	Add Optional Length-Checking To zip	Brandt Bucher	3.10
SF	621	Storing project metadata in pyproject.toml	Brett Cannon, Dustin Ingram, Paul Ganssle, Pradyun Gedam, Sébastien Eustace, Thomas Kluyver, Tzu-ping Chung	
SF	623	Remove wstr from Unicode	Inada Naoki	3.10
SF	624	Remove Py_UNICODE encoder APIs	Inada Naoki	3.11
SF	625	Filename of a Source Distribution	Tzu-ping Chung, Paul Moore	
SF	626	Precise line numbers for debugging and other tools.	Mark Shannon	3.10
SF	627	Recording installed projects	Petr Viktorin	
SF	628	Add math.tau	Alyssa Coghlan	3.6
SF	629	Versioning PyPI’s Simple API	Donald Stufft	
SF	632	Deprecate distutils module	Steve Dower	3.10
SF	634	Structural Pattern Matching: Specification	Brandt Bucher, Guido van Rossum	3.10
SF	639	Improving License Clarity with Better Package Metadata	Philippe Ombredanne, C.A.M. Gerlach, Karolina Surma	
SF	643	Metadata for Package Source Distributions	Paul Moore	
SF	644	Require OpenSSL 1.1.1 or newer	Christian Heimes	3.10
SF	646	Variadic Generics	Mark Mendoza, Matthew Rahtz, Pradeep Kumar Srinivasan, Vincent Siles	3.11
SF	647	User-Defined Type Guards	Eric Traut	3.10
SF	649	Deferred Evaluation Of Annotations Using Descriptors	Larry Hastings	3.14
SF	652	Maintaining the Stable ABI	Petr Viktorin	3.10
SF	654	Exception Groups and except*	Irit Katriel, Yury Selivanov, Guido van Rossum	3.11
SF	655	Marking individual TypedDict items as required or potentially-missing	David Foster	3.11
SF	656	Platform Tag for Linux Distributions Using Musl	Tzu-ping Chung	
SF	657	Include Fine Grained Error Locations in Tracebacks	Pablo Galindo Salgado, Batuhan Taskaya, Ammar Askar	3.11
SF	660	Editable installs for pyproject.toml based builds (wheel based)	Daniel Holth, Stéphane Bidoul	
SF	667	Consistent views of namespaces	Mark Shannon, Tian Gao	3.13
SF	669	Low Impact Monitoring for CPython	Mark Shannon	3.12
SF	670	Convert macros to functions in the Python C API	Erlend Egeberg Aasland, Victor Stinner	3.11
SF	673	Self Type	Pradeep Kumar Srinivasan, James Hilton-Balfe	3.11
SF	675	Arbitrary Literal String Type	Pradeep Kumar Srinivasan, Graham Bleaney	3.11
SF	678	Enriching Exceptions with Notes	Zac Hatfield-Dodds	3.11
SF	680	tomllib: Support for Parsing TOML in the Standard Library	Taneli Hukkinen, Shantanu Jain	3.11
SF	681	Data Class Transforms	Erik De Bonte, Eric Traut	3.11
SF	682	Format Specifier for Signed Zero	John Belmonte	3.11
SF	683	Immortal Objects, Using a Fixed Refcount	Eric Snow, Eddie Elizondo	3.12
SF	684	A Per-Interpreter GIL	Eric Snow	3.12
SF	685	Comparison of extra names for optional distribution dependencies	Brett Cannon	
SF	688	Making the buffer protocol accessible in Python	Jelle Zijlstra	3.12
SF	689	Unstable C API tier	Petr Viktorin	3.12
SF	692	Using TypedDict for more precise **kwargs typing	Franek Magiera	3.12
SF	695	Type Parameter Syntax	Eric Traut	3.12
SF	696	Type Defaults for Type Parameters	James Hilton-Balfe	3.13
SF	697	Limited C API for Extending Opaque Types	Petr Viktorin	3.12
SF	698	Override Decorator for Static Typing	Steven Troxler, Joshua Xu, Shannon Zhu	3.12
SF	700	Additional Fields for the Simple API for Package Indexes	Paul Moore	
SF	702	Marking deprecations using the type system	Jelle Zijlstra	3.13
SF	705	TypedDict: Read-only items	Alice Purcell	3.13
SF	706	Filter for tarfile.extractall	Petr Viktorin	3.12
SF	709	Inlined comprehensions	Carl Meyer	3.12
SF	715	Disabling bdist_egg distribution uploads on PyPI	William Woodruff	
SF	721	Using tarfile.data_filter for source distribution extraction	Petr Viktorin	3.12
SF	723	Inline script metadata	Ofek Lev	
SF	730	Adding iOS as a supported platform	Russell Keith-Magee	3.13
SF	734	Multiple Interpreters in the Stdlib	Eric Snow	3.14
SF	735	Dependency Groups in pyproject.toml	Stephen Rosen	
SF	737	C API to format a type fully qualified name	Victor Stinner	3.13
SF	738	Adding Android as a supported platform	Malcolm Smith	3.13
SF	740	Index support for digital attestations	William Woodruff, Facundo Tuesca, Dustin Ingram	
SF	741	Python Configuration C API	Victor Stinner	3.14
SF	742	Narrowing types with TypeIs	Jelle Zijlstra	3.13
SF	749	Implementing PEP 649	Jelle Zijlstra	3.14
SF	750	Template Strings	Jim Baker, Guido van Rossum, Paul Everitt, Koudai Aono, Lysandros Nikolaou, Dave Peck	3.14
SF	751	A file format to record Python dependencies for installation reproducibility	Brett Cannon	
SF	757	C API to import-export Python integers	Sergey B Kirpichev, Victor Stinner	3.14
SF	758	Allow except and except* expressions without parentheses	Pablo Galindo Salgado, Brett Cannon	3.14
SF	765	Disallow return/break/continue that exit a finally block	Irit Katriel, Alyssa Coghlan	3.14
SF	768	Safe external debugger interface for CPython	Pablo Galindo Salgado, Matt Wozniski, Ivona Stojanovic	3.14
SF	779	Criteria for supported status for free-threaded Python	Thomas Wouters, Matt Page, Sam Gross	3.14
SF	782	Add PyBytesWriter C API	Victor Stinner	3.15
SF	784	Adding Zstandard to the standard library	Emma Harper Smith	3.14
SF	791	math.integer — submodule for integer-specific mathematics functions	Neil Girdhar, Sergey B Kirpichev, Tim Peters, Serhiy Storchaka	3.15
SF	792	Project status markers in the simple index	William Woodruff, Facundo Tuesca	
SF	3101	Advanced String Formatting	Talin	3.0
SF	3102	Keyword-Only Arguments	Talin	3.0
SF	3104	Access to Names in Outer Scopes	Ka-Ping Yee	3.0
SF	3105	Make print a function	Georg Brandl	3.0
SF	3106	Revamping dict.keys(), .values() and .items()	Guido van Rossum	3.0
SF	3107	Function Annotations	Collin Winter, Tony Lownds	3.0
SF	3108	Standard Library Reorganization	Brett Cannon	3.0
SF	3109	Raising Exceptions in Python 3000	Collin Winter	3.0
SF	3110	Catching Exceptions in Python 3000	Collin Winter	3.0
SF	3111	Simple input built-in in Python 3000	Andre Roberge	3.0
SF	3112	Bytes literals in Python 3000	Jason Orendorff	3.0
SF	3113	Removal of Tuple Parameter Unpacking	Brett Cannon	3.0
SF	3114	Renaming iterator.next() to iterator.__next__()	Ka-Ping Yee	3.0
SF	3115	Metaclasses in Python 3000	Talin	3.0
SF	3116	New I/O	Daniel Stutzbach, Guido van Rossum, Mike Verdone	3.0
SF	3118	Revising the buffer protocol	Travis Oliphant, Carl Banks	3.0
SF	3119	Introducing Abstract Base Classes	Guido van Rossum, Talin	3.0
SF	3120	Using UTF-8 as the default source encoding	Martin von Löwis	3.0
SF	3121	Extension Module Initialization and Finalization	Martin von Löwis	3.0
SF	3123	Making PyObject_HEAD conform to standard C	Martin von Löwis	3.0
SF	3127	Integer Literal Support and Syntax	Patrick Maupin	3.0
SF	3129	Class Decorators	Collin Winter	3.0
SF	3131	Supporting Non-ASCII Identifiers	Martin von Löwis	3.0
SF	3132	Extended Iterable Unpacking	Georg Brandl	3.0
SF	3134	Exception Chaining and Embedded Tracebacks	Ka-Ping Yee	3.0
SF	3135	New Super	Calvin Spealman, Tim Delaney, Lie Ryan	3.0
SF	3137	Immutable Bytes and Mutable Buffer	Guido van Rossum	3.0
SF	3138	String representation in Python 3000	Atsuo Ishimoto	3.0
SF	3141	A Type Hierarchy for Numbers	Jeffrey Yasskin	3.0
SF	3144	IP Address Manipulation Library for the Python Standard Library	Peter Moody	3.3
SF	3147	PYC Repository Directories	Barry Warsaw	3.2
SF	3148	futures - execute computations asynchronously	Brian Quinlan	3.2
SF	3149	ABI version tagged .so files	Barry Warsaw	3.2
SF	3151	Reworking the OS and IO exception hierarchy	Antoine Pitrou	3.3
SF	3154	Pickle protocol version 4	Antoine Pitrou	3.4
SF	3155	Qualified name for classes and functions	Antoine Pitrou	3.3
SF	3156	Asynchronous IO Support Rebooted: the “asyncio” Module	Guido van Rossum	3.3
Historical Meta-PEPs and Informational PEPs
PEP	Title	Authors	
PS	5	Guidelines for Language Evolution	Paul Prescod	
PS	6	Bug Fix Releases	Aahz, Anthony Baxter	
IF	160	Python 1.6 Release Schedule	Fred L. Drake, Jr.	1.6
IF	200	Python 2.0 Release Schedule	Jeremy Hylton	2.0
IF	226	Python 2.1 Release Schedule	Jeremy Hylton	2.1
IF	251	Python 2.2 Release Schedule	Barry Warsaw, Guido van Rossum	2.2
IF	283	Python 2.3 Release Schedule	Guido van Rossum	2.3
IF	320	Python 2.4 Release Schedule	Barry Warsaw, Raymond Hettinger, Anthony Baxter	2.4
PF	347	Migrating the Python CVS to Subversion	Martin von Löwis	
IF	356	Python 2.5 Release Schedule	Neal Norwitz, Guido van Rossum, Anthony Baxter	2.5
PF	360	Externally Maintained Packages	Brett Cannon	
IF	361	Python 2.6 and 3.0 Release Schedule	Neal Norwitz, Barry Warsaw	2.6, 3.0
IF	373	Python 2.7 Release Schedule	Benjamin Peterson	2.7
PF	374	Choosing a distributed VCS for the Python project	Brett Cannon, Stephen J. Turnbull, Alexandre Vassalotti, Barry Warsaw, Dirkjan Ochtman	
IF	375	Python 3.1 Release Schedule	Benjamin Peterson	3.1
PF	385	Migrating from Subversion to Mercurial	Dirkjan Ochtman, Antoine Pitrou, Georg Brandl	
IF	392	Python 3.2 Release Schedule	Georg Brandl	3.2
IF	398	Python 3.3 Release Schedule	Georg Brandl	3.3
IF	404	Python 2.8 Un-release Schedule	Barry Warsaw	2.8
IF	429	Python 3.4 Release Schedule	Larry Hastings	3.4
PS	438	Transitioning to release-file hosting on PyPI	Holger Krekel, Carl Meyer	
PF	449	Removal of the PyPI Mirror Auto Discovery and Naming Scheme	Donald Stufft	
PF	464	Removal of the PyPI Mirror Authenticity API	Donald Stufft	
PF	470	Removing External Hosting Support on PyPI	Donald Stufft	
IF	478	Python 3.5 Release Schedule	Larry Hastings	3.5
IF	494	Python 3.6 Release Schedule	Ned Deily	3.6
PF	512	Migrating from hg.python.org to GitHub	Brett Cannon	
IF	537	Python 3.7 Release Schedule	Ned Deily	3.7
PF	541	Package Index Name Retention	Łukasz Langa	
IF	569	Python 3.8 Release Schedule	Łukasz Langa	3.8
PF	581	Using GitHub Issues for CPython	Mariatta	
IF	596	Python 3.9 Release Schedule	Łukasz Langa	3.9
PF	3000	Python 3000	Guido van Rossum	
PF	3002	Procedure for Backwards-Incompatible Changes	Steven Bethard	
PF	3003	Python Language Moratorium	Brett Cannon, Jesse Noller, Guido van Rossum	
PF	3099	Things that will Not Change in Python 3000	Georg Brandl	
PF	3100	Miscellaneous Python 3.0 Plans	Brett Cannon	
PF	8001	Python Governance Voting Process	Brett Cannon, Christian Heimes, Donald Stufft, Eric Snow, Gregory P. Smith, Łukasz Langa, Mariatta, Nathaniel J. Smith, Pablo Galindo Salgado, Raymond Hettinger, Tal Einat, Tim Peters, Zachary Ware	
Deferred PEPs (postponed pending further research or updates)
PEP	Title	Authors	
SD	213	Attribute Access Handlers	Paul Prescod	2.1
SD	219	Stackless Python	Gordon McMillan	2.1
SD	222	Web Library Enhancements	A.M. Kuchling	2.1
SD	233	Python Online Help	Paul Prescod	2.1
SD	267	Optimized Access to Module Namespaces	Jeremy Hylton	2.2
SD	269	Pgen Module for Python	Jonathan Riehl	2.2
SD	280	Optimizing access to globals	Guido van Rossum	2.3
SD	286	Enhanced Argument Tuples	Martin von Löwis	2.3
SD	312	Simple Implicit Lambda	Roman Suzi, Alex Martelli	2.4
SD	316	Programming by Contract for Python	Terence Way	
SD	323	Copyable Iterators	Alex Martelli	2.5
SD	337	Logging Usage in the Standard Library	Michael P. Dubner	2.5
SD	368	Standard image protocol and class	Lino Mastrodomenico	2.6, 3.0
SD	400	Deprecate codecs.StreamReader and codecs.StreamWriter	Victor Stinner	3.3
SD	403	General purpose decorator clause (aka “@in” clause)	Alyssa Coghlan	3.4
PD	407	New release cycle and introducing long-term support versions	Antoine Pitrou, Georg Brandl, Barry Warsaw	
SD	419	Protecting cleanup statements from interruptions	Paul Colomiets	3.3
ID	423	Naming conventions and recipes related to packaging	Benoit Bryon	
ID	444	Python Web3 Interface	Chris McDonough, Armin Ronacher	
SD	447	Add __getdescriptor__ method to metaclass	Ronald Oussoren	
SD	491	The Wheel Binary Package Format 1.9	Daniel Holth	
SD	499	python -m foo should also bind ‘foo’ in sys.modules	Cameron Simpson, Chris Angelico, Joseph Jevnik	3.10
SD	505	None-aware operators	Mark E. Haase, Steve Dower	3.8
SD	532	A circuit breaking protocol and binary operators	Alyssa Coghlan, Mark E. Haase	3.8
SD	533	Deterministic cleanup for iterators	Nathaniel J. Smith	
SD	534	Improved Errors for Missing Standard Library Modules	Tomáš Orsava, Petr Viktorin, Alyssa Coghlan	
SD	535	Rich comparison chaining	Alyssa Coghlan	3.8
SD	547	Running extension modules using the -m option	Marcel Plch, Petr Viktorin	3.7
SD	556	Threaded garbage collection	Antoine Pitrou	3.7
SD	568	Generator-sensitivity for Context Variables	Nathaniel J. Smith	3.8
SD	661	Sentinel Values	Tal Einat	
SD	674	Disallow using macros as l-values	Victor Stinner	3.12
SD	774	Removing the LLVM requirement for JIT builds	Savannah Ostrowski	3.14
SD	778	Supporting Symlinks in Wheels	Emma Harper Smith	
SD	787	Safer subprocess usage using t-strings	Nick Humrich, Alyssa Coghlan	3.15
SD	3124	Overloading, Generic Functions, Interfaces, and Adaptation	Phillip J. Eby	
SD	3143	Standard daemon process library	Ben Finney	3.x
SD	3150	Statement local namespaces (aka “given” clause)	Alyssa Coghlan	3.4
