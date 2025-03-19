![Last Sync](https://img.shields.io/badge/Last_Sync-February_17,_2024-brightgreen)

# The Old New Win32API

This page provides a list of links to subset of posts of Raymond Chen's famous
blog **[The Old New Thing](https://devblogs.microsoft.com/oldnewthing/)**. The
subset is limited mainly to Win32API and some COM-related stuff. 

The reason why I maintain this page is that it often provides information which
is missing on MSDN or which is described there in a cryptic way, and also
because the blog is not easily searchable.

The links here are categorized by their topic instead of a chronological order.
Sometimes, when appropriate, a single post may be put into multiple categories.

In some (quite rare) cases, links to other sources are included if they are
found useful.

**Disclaimer:** I am not claiming authorship of any linked contents. This is
only about hopefully useful organization of the great articles Raymond has
written over the years.


## Table of Contents

* [Processes and Threads](#processes-and-threads)
  * [Processes](#processes)
  * [Threads](#threads)
  * [Thread Pools](#thread-pools)
  * [Thread Affinity of Objects](#thread-affinity-of-objects)
  * [Thread Stack](#thread-stack)
  * [Fibers](#fibers)
* [Synchronization](#synchronization)
  * [`WaitOnAddress()`](#waitonaddress)
  * [`WaitForMultipleObjects()` and Relatives](#waitformultipleobjects-and-relatives)
  * [Lock-Free Patterns](#lock-free-patterns)
* [DLLs](#dlls)
  * [`DllMain()`](#dllmain)
* [Resources](#resources)
  * [Bitmap and Icon Resources](#bitmap-and-icon-resources)
  * [Dialog Templates](#dialog-templates)
  * [Menu Templates and Accelerator Resources](#menu-templates-and-accelerator-resources)
  * [String Resources](#string-resources)
  * [Version Templates](#version-templates)
  * [Data and Custom Resources](#data-and-custom-resources)
* [Application (as a whole)](#application-as-a-whole)
  * [Command Line](#command-line)
  * [Taskbar](#taskbar)
* [`HWND` (General Point of View)](#hwnd-general-point-of-view)
  * [Windows Hierarchy](#windows-hierarchy)
  * [Window Styles](#window-styles)
  * [Window Classes](#window-classes)
* [Top-Level Windows](#top-level-windows)
  * [Window Frame and Caption](#window-frame-and-caption)
  * [DWM](#dwm)
  * [Dialogs](#dialogs)
  * [Nested and Embedded Dialogs](#nested-and-embedded-dialogs)
  * [Common Dialogs](#common-dialogs)
  * [Control Navigation](#control-navigation)
  * [Dialog Manager](#dialog-manager)
  * [Modality](#modality)
  * [Property Sheets](#property-sheets)
* [Controls](#controls)
  * [Animation Controls](#animation-controls)
  * [Buttons](#buttons)
  * [Combo Boxes](#combo-boxes)
  * [Edit Controls](#edit-controls)
  * [List Views](#list-views)
  * [Rich Text Controls](#rich-text-controls)
  * [Scrollbars](#scrollbars)
  * [Static Controls](#static-controls)
  * [Toolbars](#toolbars)
  * [Tooltips](#tooltips)
  * [Trackbars](#trackbars)
  * [Tree List Views](#tree-list-views)
* [Processing of Messages](#processing-of-messages)
  * [Hooking](#hooking)
* [Specific Messages](#specific-messages)
  * [Notifications](#notifications)
  * [Window Construction and Destruction](#window-construction-and-destruction)
  * [Window Geometry Messages](#window-geometry-messages)
  * [Window Painting Messages](#window-painting-messages)
  * [Window Focus Messages](#window-focus-messages)
  * [Keyboard Messages](#keyboard-messages)
  * [Mouse Messages](#mouse-messages)
  * [Dialog Messages](#dialog-mesages)
  * [Other Window Messages](#other-window-messages)
  * [System Messages](#system-messages)
* [GDI](#gdi)
  * [Cursors](#cursors)
  * [Brushes](#brushes)
  * [Pens](#pens)
  * [Bitmaps](#bitmaps)
  * [DIB](#dib)
  * [`LockWindowUpdate()`](#lockwindowupdate)
  * [Painting Standard Elements](#painting-standard-elements)
  * [`UXTHEME.DLL`](#uxthemedll)
  * [Multiple Monitors](#multiple-monitors)
* [Accessibility](#accessibility)
* [COM](#com)
  * [Declaring COM Interfaces](#declaring-com-interfaces)
  * [COM Apartments](#com-apartments)
  * [COM Initialization](#com-initialization)
  * [COM Static Store](#com-static-store)
  * [COM Marshaling](#com-marshaling)
  * [COM Error Handling](#com-error-handling)
  * [COM Asynchronous Interfaces](#com-asynchronous-interfaces)
  * [GUIDs](#guids)
  * [COM Strings](#com-strings)
  * [COM Variants](#com-variants)
  * [`IUnknown`](#iunknown)
  * [`IMoniker`](#imoniker)
  * [`ICallback`](#icallback)
  * [`IContextMenu`](#icontextmenu)
  * [`IFileDialog`](#ifiledialog)
  * [`IMultiLanguage`](#imultilanguage)
  * [`INamespaceWalk`](#inamespacewalk)
  * [`IStream`](#istream)
  * [`IVirtual­Desktop­Manager`](#ivirtual­desktop­manager)
  * [Clipboard](#clipboard)
  * [Drag and Drop](#drag-and-drop)
  * [Enumeration](#enumeration)
  * [Shell](#shell)
  * [Uncategorized COM Stuff](#uncategorized-com-stuff)
* [Memory](#memory)
* [Input and Output](#input-and-output)
  * [Asynchronous Input and Output](#asynchronous-input-and-output)
  * [Files and Directories](#files-and-directories)
  * [ACL](#acl)
* [Security Permissions, Attributes and Identifiers](#security-permissions-attributes-and-identifiers)
* [Registry](#registry)
* [Strings and Locales](#strings-and-locales)
* [NT Services](#nt-services)
* [Uncategorized](#uncategorized)


## Processes and Threads

### Processes
* [`CreateProcess` does not wait for the process to start](https://devblogs.microsoft.com/oldnewthing/20050119-00/?p=36663)
* [Why does the `CreateProcess` function modify its input command line?](https://devblogs.microsoft.com/oldnewthing/20090601-00/?p=18083)
* [Why do people take a lock around `CreateProcess` calls?](https://devblogs.microsoft.com/oldnewthing/20200306-00/?p=103538)
* [Disabling the program crash dialog](https://devblogs.microsoft.com/oldnewthing/20040727-00/?p=38323)
* [How do I pass a lot of data to a process when it starts up?](https://devblogs.microsoft.com/oldnewthing/20031211-00/?p=41543)
* [What was the purpose of the `hPrevInstance` parameter to `WinMain`?](https://devblogs.microsoft.com/oldnewthing/20040615-00/?p=38873)
* [Is `RunAsInvoker` a secret, even higher UAC setting?](https://devblogs.microsoft.com/oldnewthing/20161117-00/?p=94735)
* [How do I prevent a child process from displaying the Windows Error Reporting dialog?](https://devblogs.microsoft.com/oldnewthing/20160204-00/?p=92972)
* [How is it that `WriteProcessMemory` succeeds in writing to read-only memory?](https://devblogs.microsoft.com/oldnewthing/?p=100415)
* [Is it a good idea to let `WriteProcessMemory` manage the page protection for me?](https://devblogs.microsoft.com/oldnewthing/20190729-00/?p=102737)
* [How can I launch an unelevated process from my elevated process, redux](https://devblogs.microsoft.com/oldnewthing/20190425-00/?p=102443)
* [How can I check the integrity level of my process?](https://devblogs.microsoft.com/oldnewthing/20221017-00/?p=107291)
* [Is it true that raising a structured exception from a structured exception handler terminates the process?](https://devblogs.microsoft.com/oldnewthing/20221020-00/?p=107303)
* [A more direct and mistake-free way of creating a process in a job object](https://devblogs.microsoft.com/oldnewthing/20230209-00/?p=107812)

### Threads
* [Invalid thread and process IDs](https://devblogs.microsoft.com/oldnewthing/20040223-00/?p=40503)
* [Why does my thread handle suddenly go bad? All I did was wait on it!](https://devblogs.microsoft.com/oldnewthing/20170929-00/?p=97115)
* [What happens if you simply return from the thread callback passed to `_beginthread` and `_beginthreadex`?](https://devblogs.microsoft.com/oldnewthing/20171115-00/?p=97405)
* [Why you should never suspend a thread](https://devblogs.microsoft.com/oldnewthing/20031209-00/?p=41573)
* [The dangers of sleeping on a UI thread](https://devblogs.microsoft.com/oldnewthing/20060210-00/?p=32323)
* [In pursuit of the message queue](https://devblogs.microsoft.com/oldnewthing/20060221-09/?p=32203)
* [Enumerating threads in a process](https://devblogs.microsoft.com/oldnewthing/20060223-14/?p=32173)
* [Win32 user interface work is inherently single-threaded](https://devblogs.microsoft.com/oldnewthing/20071018-00/?p=24743)
* [How bad is it to delay closing a thread handle for a long time after the thread has exited?](https://devblogs.microsoft.com/oldnewthing/20161215-00/?p=94945)
* [If I call `GetExitCodeThread` for a thread that I know for sure has exited, why does it still say `STILL_ACTIVE`?](https://devblogs.microsoft.com/oldnewthing/20180302-00/?p=98145)
* [Is there a problem with `Create­Remote­Thread` on 64-bit systems?](https://devblogs.microsoft.com/oldnewthing/20180615-00/?p=99025)
* [Is the `Terminate­Thread` function synchronous?](https://devblogs.microsoft.com/oldnewthing/20180727-00/?p=99355)
* [Removing the `Terminate­Thread` from code that waits for a job object to empty](https://devblogs.microsoft.com/oldnewthing/20180831-00/?p=99625)
* [What is the point of `FreeLibraryAndExitThread`?](https://devblogs.microsoft.com/oldnewthing/20131105-00/?p=2733)
* [What happens if I give contradictory values for the stack commit and stack reserve?](https://devblogs.microsoft.com/oldnewthing/20210107-00/?p=104680)

### Thread Pools
* [What exactly does the `msWindowLength` parameter to `SetThreadpoolTimer` mean?](https://devblogs.microsoft.com/oldnewthing/20160914-00/?p=94315)
* [What’s the difference between `CreateTimerQueueTimer` and `SetThreadpoolTimer`?](https://devblogs.microsoft.com/oldnewthing/20180308-00/?p=98185)
* [How to avoid accessing freed memory when canceling a thread pool callback](https://devblogs.microsoft.com/oldnewthing/20180502-00/?p=98655)
* [Avoiding deadlocks when cancelling a thread pool callback, part 1: External callback data](https://devblogs.microsoft.com/oldnewthing/20180503-00/?p=98665)
* [Avoiding deadlocks when cancelling a thread pool callback, part 2: Referring back to the containing object](https://devblogs.microsoft.com/oldnewthing/20180504-00/?p=98675)
* [Gotcha: A threadpool periodic timer will not wait for the previous tick to complete](https://devblogs.microsoft.com/oldnewthing/20200217-00/?p=103441)
* [Why am I getting an exception from the thread pool during process shutdown?](https://devblogs.microsoft.com/oldnewthing/20200130-00/?p=103385)
* [What happens to the value returned from the function passed to `Queue­User­Work­Item`?](https://devblogs.microsoft.com/oldnewthing/20210121-00/?p=104746)
* [The mental model for `StartThreadpoolIo`](https://devblogs.microsoft.com/oldnewthing/20211117-00/?p=105933)
* [How can I detect that a thread pool work item is taking too long?](https://devblogs.microsoft.com/oldnewthing/20220110-00/?p=106139)
* [How can I close a thread pool and cancel all work that had been queued to it?](https://devblogs.microsoft.com/oldnewthing/20240205-00/?p=109360)


### Thread Affinity of Objects
* [Thread affinity of user interface objects, part 1: Window handles](https://devblogs.microsoft.com/oldnewthing/20051010-09/?p=33843)
* [Thread affinity of user interface objects, part 2: Device contexts](https://devblogs.microsoft.com/oldnewthing/20051011-10/?p=33823)
* [Thread affinity of user interface objects, part 3: Menus, icons, cursors, and accelerator tables](https://devblogs.microsoft.com/oldnewthing/20051012-00/?p=33803)
* [Thread affinity of user interface objects, part 4: GDI objects and other notes on affinity](https://devblogs.microsoft.com/oldnewthing/20051013-11/?p=33783)
* [Thread affinity of user interface objects, part 5: Object clean-up](https://devblogs.microsoft.com/oldnewthing/20051014-19/?p=33763)
* [Thread affinity of user interface objects: Addendum](https://devblogs.microsoft.com/oldnewthing/20121109-00/?p=6133)

### Thread Stack
* [How can I expand my thread’s stack at runtime?](https://devblogs.microsoft.com/oldnewthing/20200601-00/?p=103815)
* [Using fibers to expand a thread’s stack at runtime, part 1](https://devblogs.microsoft.com/oldnewthing/20200602-00/?p=103819)
* [Using fibers to expand a thread’s stack at runtime, part 2](https://devblogs.microsoft.com/oldnewthing/20200603-00/?p=103824)
* [Using fibers to expand a thread’s stack at runtime, part 3](https://devblogs.microsoft.com/oldnewthing/20200604-00/?p=103833)
* [Using fibers to expand a thread’s stack at runtime, part 4](https://devblogs.microsoft.com/oldnewthing/20200605-00/?p=103840)
* [Using fibers to expand a thread’s stack at runtime, part 5](https://devblogs.microsoft.com/oldnewthing/20200611-00/?p=103858)
* [Using fibers to expand a thread’s stack at runtime, part 6](https://devblogs.microsoft.com/oldnewthing/20200612-00/?p=103865)
* [Comparing fibers to threads for the purpose of expanding a thread’s stack at runtime](https://devblogs.microsoft.com/oldnewthing/20200608-00/?p=103844)
* [Determining approximately how much stack space is available, part 1](https://devblogs.microsoft.com/oldnewthing/20200609-00/?p=103847)
* [Determining approximately how much stack space is available, part 2](https://devblogs.microsoft.com/oldnewthing/20200610-00/?p=103855)

### Fibers
* [What happens to the fibers which ran on a thread when the thread exits?](https://devblogs.microsoft.com/oldnewthing/20100225-00/?p=14813)
* [It's fine to use fibers, but everybody has to be on board with the plan](https://devblogs.microsoft.com/oldnewthing/20100226-00/?p=14793)
* [Fibers aren’t useful for much any more; there’s just one corner of it that remains useful for a reason unrelated to fibers](https://devblogs.microsoft.com/oldnewthing/20191011-00/?p=102989)


## Synchronization

* [Understanding the consequences of `WAIT_ABANDONED`](https://devblogs.microsoft.com/oldnewthing/20050912-14/?p=34253)
* [Windows keyed events, critical sections, and new Vista synchronization features](http://joeduffyblog.com/2006/11/28/windows-keyed-events-critical-sections-and-new-vista-synchronization-features/)
* [Combining the work queue of distinct events, order not important, with an auto-reset event](https://devblogs.microsoft.com/oldnewthing/20170616-00/?p=96405)
* [How fair are SRW locks, particularly when there are both readers and writers?](https://devblogs.microsoft.com/oldnewthing/20170705-00/?p=96535)
* [You can use a file as a synchronization object, too](https://devblogs.microsoft.com/oldnewthing/20140905-00/?p=63)
* [Can I wait for a kernel event to become *unsignaled*?](https://devblogs.microsoft.com/oldnewthing/20200305-00/?p=103535)
* [If the slim reader/writer lock (`SRWLOCK`) doesn’t remember who the shared lock owner is, does that mean it’s okay to acquire it recursively?](https://devblogs.microsoft.com/oldnewthing/20220304-00/?p=106309)

### `WaitOnAddress()`
* [`WaitOnAddress` lets you create a synchronization object out of any data variable, even a byte](https://devblogs.microsoft.com/oldnewthing/20160823-00/?p=94145)
* [Implementing a synchronization barrier in terms of `WaitOnAddress`](https://devblogs.microsoft.com/oldnewthing/20160824-00/?p=94155)
* [Implementing a critical section in terms of `WaitOnAddress`](https://devblogs.microsoft.com/oldnewthing/20160825-00/?p=94165)
* [Extending our critical section based on `WaitOnAddress` to support timeouts](https://devblogs.microsoft.com/oldnewthing/20170531-00/?p=96255)
* [Comparing `WaitOnAddress` with futexes (futexi? futexen?)](https://devblogs.microsoft.com/oldnewthing/20170601-00/?p=96265)
* [Creating a semaphore from `WaitOnAddress`](https://devblogs.microsoft.com/oldnewthing/20170612-00/?p=96375)
* [Creating a semaphore with a maximum count from `WaitOnAddress`](https://devblogs.microsoft.com/oldnewthing/20170613-00/?p=96385)
* [Creating a manual-reset event from `WaitOnAddress`](https://devblogs.microsoft.com/oldnewthing/20170614-00/?p=96395)
* [Creating an automatic-reset event from `WaitOnAddress`](https://devblogs.microsoft.com/oldnewthing/20170615-00/?p=96396)

### `WaitForMultipleObjects()` and Relatives

* [`MsgWaitForMultipleObjects` and the queue state](https://devblogs.microsoft.com/oldnewthing/20050217-00/?p=36423)
* [You can call `MsgWaitForMultipleObjects` with zero handles](https://devblogs.microsoft.com/oldnewthing/20060125-18/?p=32533)
* [Pumping messages while waiting for a period of time](https://devblogs.microsoft.com/oldnewthing/20060126-00/?p=32513)
* [Waiting for all handles with `MsgWaitForMultipleObjects` is a bug waiting to happen](https://devblogs.microsoft.com/oldnewthing/20060127-17/?p=32493)
* [Why does `WaitForMultipleObjects` return `ERROR_INVALID_PARAMETER` when all the parameters look valid to me?](https://devblogs.microsoft.com/oldnewthing/20110225-00/?p=11383)
* [If more than one object causes a `WaitForMultipleObjects` to return, how do I find out about the other ones?](https://devblogs.microsoft.com/oldnewthing/20150409-00/?p=44273)
* [What’s the point of passing a never-signaled event to `MsgWaitForMultipleObjects`?](https://devblogs.microsoft.com/oldnewthing/20181114-00/?p=100215)

### Lock-Free Patterns
* [Lock free many-producer/single-consumer patterns: A work queue with task coalescing](https://devblogs.microsoft.com/oldnewthing/20161121-00/?p=94755)
* [Lock free many-producer/single-consumer patterns: A work queue where the last one wins](https://devblogs.microsoft.com/oldnewthing/20161122-00/?p=94765)
* [Lock free many-producer/single-consumer patterns: A work queue of identical non-coalescable events](https://devblogs.microsoft.com/oldnewthing/20161123-00/?p=94766)
* [Lock free many-producer/single-consumer patterns: A work queue of distinct events, order not important](https://devblogs.microsoft.com/oldnewthing/20161124-00/?p=94775)
* [Lock free many-producer/single-consumer patterns: A work queue of distinct events, FIFO](https://devblogs.microsoft.com/oldnewthing/20161125-00/?p=94795)
* [Lock free many-producer/single-consumer patterns: A work queue of distinct events, order not important, follow-up question](https://devblogs.microsoft.com/oldnewthing/20180627-00/?p=99105)


## DLLs

* [Don't trust the return address](https://devblogs.microsoft.com/oldnewthing/20040101-00/?p=41223)
* [Why can't I `GetProcAddress` a function I dllexport'ed?](https://devblogs.microsoft.com/oldnewthing/20040112-00/?p=41083)
* [What is the difference between `HINSTANCE` and `HMODULE`?](https://devblogs.microsoft.com/oldnewthing/20040614-00/?p=38903)
* [Accessing the current module's `HINSTANCE` from a static library](https://devblogs.microsoft.com/oldnewthing/20041025-00/?p=37483)
* [`LoadLibraryEx(DONT_RESOLVE_DLL_REFERENCES)` is fundamentally flawed](https://devblogs.microsoft.com/oldnewthing/20050214-00/?p=36463)
* [Why are DLLs unloaded in the "wrong" order?](https://devblogs.microsoft.com/oldnewthing/20050523-05/?p=35573)
* [How are DLL functions exported in 32-bit Windows?](https://devblogs.microsoft.com/oldnewthing/20060718-32/?p=30483)
* [Exported functions that are really forwarders](https://devblogs.microsoft.com/oldnewthing/?p=30473)
* [Rethinking the way DLL exports are resolved for 32-bit Windows](https://devblogs.microsoft.com/oldnewthing/20060720-20/?p=30453)
* [Names in the import library are decorated for a reason](https://devblogs.microsoft.com/oldnewthing/20060727-00/?p=30343)
* [What happens when you get dllimport wrong?](https://devblogs.microsoft.com/oldnewthing/20060726-00/?p=30363)
* [Issues related to forcing a stub to be created for an imported function](https://devblogs.microsoft.com/oldnewthing/20060725-00/?p=30383)
* [Allocating and freeing memory across module boundaries](https://devblogs.microsoft.com/oldnewthing/20060915-04/?p=29723)
* [DLL forwarding is not the same as delay-loading](https://devblogs.microsoft.com/oldnewthing/20080204-00/?p=23593)
* [What is DLL import hinting?](https://devblogs.microsoft.com/oldnewthing/20100317-00/?p=14573)
* [What is DLL import binding?](https://devblogs.microsoft.com/oldnewthing/20100318-00/?p=14563)
* [What is the point of `FreeLibraryAndExitThread`?](https://devblogs.microsoft.com/oldnewthing/20131105-00/?p=2733)
* [A library loaded via `LOAD_LIBRARY_AS_DATAFILE` (or similar flags) doesn't get to play in any reindeer module games](https://devblogs.microsoft.com/oldnewthing/20141120-00/?p=43573)
* [Could there be any problems with calling `GetModuleFileNameEx` on your own process?](https://devblogs.microsoft.com/oldnewthing/20160310-00/?p=93141)
* [How can I specify that my DLL should resolve a DLL dependency from the same directory that the DLL is in?](https://devblogs.microsoft.com/oldnewthing/20171011-00/?p=97195)
* [After I made my DLL delay-load another DLL, my DLL has started crashing in its process detach code](https://devblogs.microsoft.com/oldnewthing/20190718-00/?p=102719)
* [The different kinds of DLL planting](https://devblogs.microsoft.com/oldnewthing/20191231-00/?p=103282)
* [Why does `GetModuleInfo` fail to produce an entry point for executables?](https://devblogs.microsoft.com/oldnewthing/20211014-00/?p=105800)
* [What does the `SizeOfImage` mean in the `MODULEINFO` structure?](https://devblogs.microsoft.com/oldnewthing/20211015-00/?p=105802)
* [How do I suppress the error box that appears when a `LoadLibrary` fails?](https://devblogs.microsoft.com/oldnewthing/20240208-00/?p=109374)

### `DllMain()`
* [Some reasons not to do anything scary in your `DllMain`](https://devblogs.microsoft.com/oldnewthing/20040127-00/?p=40873)
* [Another reason not to do anything scary in your `DllMain`: Inadvertent deadlock](https://devblogs.microsoft.com/oldnewthing/20040128-00/?p=40853)
* [Some reasons not to do anything scary in your `DllMain`, part 3](https://devblogs.microsoft.com/oldnewthing/20140821-00/?p=183)
* [The thread that gets the `DLL_PROCESS_DETACH` notification is not necessarily the one that got the `DLL_PROCESS_ATTACH notification`](https://devblogs.microsoft.com/oldnewthing/20090626-00/?p=17733)
* [How you might be loading a DLL during `DLL_PROCESS_DETACH` without even realizing it](https://devblogs.microsoft.com/oldnewthing/20100115-00/?p=15253)
* [When `DLL_PROCESS_DETACH` tells you that the process is exiting, your best bet is just to return without doing anything](https://devblogs.microsoft.com/oldnewthing/20120105-00/?p=8683)


## Resources

* [The Resource Compiler defaults to `CP_ACP`, even in the face of subtle hints that the file is UTF-8](https://devblogs.microsoft.com/oldnewthing/20190607-00/?p=102569)
* [The relationship between module resources and resource-derived objects in 32-bit Windows](https://devblogs.microsoft.com/oldnewthing/20131003-00/?p=3043)
* [What's the difference between `FreeResource` and, say, `DestroyAcceleratorTable`](https://devblogs.microsoft.com/oldnewthing/20110307-00/?p=11283)
* [PE resources must be 4-byte aligned, but that doesn't stop people from trying other alignments](https://devblogs.microsoft.com/oldnewthing/20110609-00/?p=10463)
* [How can I tell that somebody used the `MAKEINTRESOURCE` macro to smuggle an integer inside a pointer?](https://devblogs.microsoft.com/oldnewthing/20130925-00/?p=3123)
* [Horrifically nasty gotcha: `FindResource` and `FindResourceEx`](https://devblogs.microsoft.com/oldnewthing/20150101-00/?p=43243)

### Bitmap and Icon Resources
* [Why are device-independent bitmaps upside down?](https://devblogs.microsoft.com/oldnewthing/20210525-00/?p=105250)
* [The format of bitmap resources](https://devblogs.microsoft.com/oldnewthing/20091211-00/?p=15693)
* [The format of icon resources](https://devblogs.microsoft.com/oldnewthing/20120720-00/?p=7083)
* [The format of icon resources, revisited](https://devblogs.microsoft.com/oldnewthing/20231025-00/?p=108925)
* [The evolution of the ICO file format, part 1: Monochrome beginnings](https://devblogs.microsoft.com/oldnewthing/20101018-00/?p=12513)
* [The evolution of the ICO file format, part 2: Now in color!](https://devblogs.microsoft.com/oldnewthing/20101019-00/?p=12503)
* [The evolution of the ICO file format, part 3: Alpha-blended images](https://devblogs.microsoft.com/oldnewthing/20101021-00/?p=12483)
* [The evolution of the ICO file format, part 4: PNG images](https://devblogs.microsoft.com/oldnewthing/20101022-00/?p=12473)
* [How do I set the alpha channel of a GDI bitmap to 255?](https://devblogs.microsoft.com/oldnewthing/20210915-00/?p=105687)

### Message String Resources
* [Why does `Format­Message` say that `%0` terminates the message without a trailing newline? Is it secretly adding newlines?](https://devblogs.microsoft.com/oldnewthing/20191025-00/?p=103025)

### Dialog Templates
* [On the difficulty of getting pixel-perfect layout in Win32 dialog templates](https://devblogs.microsoft.com/oldnewthing/20180510-00/?p=98725)
* [The evolution of dialog templates - 32-bit Classic Templates](https://devblogs.microsoft.com/oldnewthing/20040621-00/?p=38793)
* [The evolution of dialog templates - 32-bit Extended Templates](https://devblogs.microsoft.com/oldnewthing/20040623-00/?p=38753)
* [The evolution of dialog templates - Summary](https://devblogs.microsoft.com/oldnewthing/?p=38733)
* [The resource compiler will helpfully add window styles for you, but if you're building a dialog template yourself, you don't get that help](https://devblogs.microsoft.com/oldnewthing/20121122-00/?p=6023)

### Menu Templates and Accelerator Resources
* [The evolution of menu templates: Introduction](https://devblogs.microsoft.com/oldnewthing/20080708-00/?p=21713)
* [The evolution of menu templates: 32-bit classic menus](https://devblogs.microsoft.com/oldnewthing/20080711-00/?p=21653)
* [The evolution of menu templates: 32-bit extended menus](https://devblogs.microsoft.com/oldnewthing/20080716-00/?p=21603)
* [The format of accelerator table resources](https://devblogs.microsoft.com/oldnewthing/20040130-00/?p=40813)

### String Resources
* [The format of string resources](https://devblogs.microsoft.com/oldnewthing/20040130-00/?p=40813)
* [`LoadString` can load strings with embedded nulls, but your wrapper function might not](https://devblogs.microsoft.com/oldnewthing/20091009-00/?p=16423)

### Version Templates
* [The evolution of version resources - 32-bit version resources](https://devblogs.microsoft.com/oldnewthing/20061221-02/?p=28643)
* [The evolution of version resources - corrupted 32-bit version resources](https://devblogs.microsoft.com/oldnewthing/20061222-00/?p=28623)

### Data and Custom Resources
* [The format of data and custom resources](https://devblogs.microsoft.com/oldnewthing/20130828-00/?p=3383)


## Application (as a whole)

* [Which windows appear in the `Alt+Tab` list?](https://devblogs.microsoft.com/oldnewthing/20071008-00/?p=24863)
* [Windows Vista changed the `Alt+Tab` order slightly](https://devblogs.microsoft.com/oldnewthing/20080701-00/?p=21793)
* [Win32 user interface work is inherently single-threaded](https://devblogs.microsoft.com/oldnewthing/20071018-00/?p=24743)
* [When does `STARTF_USESHOWWINDOW` override the parameter passed to `ShowWindow`?](https://devblogs.microsoft.com/oldnewthing/20100301-00/?p=14773)
* [`WaitForInputIdle` should really be called `WaitForProcessStartupComplete`](https://devblogs.microsoft.com/oldnewthing/20100325-00/?p=14493)
* [`WaitForInputIdle` waits for any thread, which might not be the thread you care about](https://devblogs.microsoft.com/oldnewthing/20100326-00/?p=14483)
* [What are the conventions for managing standard handles?](https://devblogs.microsoft.com/oldnewthing/20130307-00/?p=5033)
* [Standard handles are really meant for single-threaded programs](https://devblogs.microsoft.com/oldnewthing/20141008-00/?p=43893)
* [If only DLLs can get `DllMain` notifications, how can an EXE receive a notification when a thread is created (for example)?](https://devblogs.microsoft.com/oldnewthing/20141016-00/?p=43833)

### Command Line
* [The first word on the command line is the program name only by convention](https://devblogs.microsoft.com/oldnewthing/20060515-07/?p=31203)
* [How is the `CommandLineToArgvW` function intended to be used?](https://devblogs.microsoft.com/oldnewthing/20100916-00/?p=12843)
* [What's up with the strange treatment of quotation marks and backslashes by `CommandLineToArgvW`](https://devblogs.microsoft.com/oldnewthing/20100917-00/?p=12833)

### Taskbar
* [How do I prevent users from pinning my program to the taskbar?](https://devblogs.microsoft.com/oldnewthing/20110601-00/?p=10523)
* [Instead of creating something and then trying to hide it, simply don't create it in the first place](https://devblogs.microsoft.com/oldnewthing/20120222-00/?p=8253) (tray icon)
* [What if my application is really two applications bundled into a single file, and I want them collected into two groups on the taskbar in Windows 7?](https://devblogs.microsoft.com/oldnewthing/20120817-00/?p=6833)
* [How do I customize how my application windows are grouped in the Taskbar?](https://devblogs.microsoft.com/oldnewthing/20120820-00/?p=6813)
* [Display an overlay on the taskbar button](https://devblogs.microsoft.com/oldnewthing/20130211-00/?p=5283)
* [Display control buttons on your taskbar preview window](https://devblogs.microsoft.com/oldnewthing/20130218-00/?p=5223)
* [Display a custom thumbnail for your application (and while you're at it, a custom live preview)](https://devblogs.microsoft.com/oldnewthing/20130225-00/?p=5153)
* [How can I query the location of the taskbar on secondary monitors?](https://devblogs.microsoft.com/oldnewthing/20141218-00/?p=43353)
* [How did that program manage to pin itself to my taskbar when I installed it?](https://devblogs.microsoft.com/oldnewthing/20141230-00/?p=43273)
* [What if I have two programs that are logically a single application, and I want them to be treated as a single group on the taskbar?](https://devblogs.microsoft.com/oldnewthing/20150810-00/?p=91141)
* [Why does the taskbar icon for grouped windows change to something weird?](https://devblogs.microsoft.com/oldnewthing/20150812-00/?p=91831)


## `HWND` (General Point of View)

* [What does it mean for a window to be Unicode?](https://devblogs.microsoft.com/oldnewthing/20180906-00/?p=99665)
* [How can I get the actual window procedure address and not a thunk?](https://devblogs.microsoft.com/oldnewthing/20180720-00/?p=99295)
* [What are these strange values returned from `GWLP_WNDPROC`?](https://devblogs.microsoft.com/oldnewthing/20031201-00/?p=41673)
* [The bonus window bytes at `GWLP_USERDATA`](https://devblogs.microsoft.com/oldnewthing/20050303-00/?p=36293)
* [What is the difference between `WM_DESTROY` and `WM_NCDESTROY`?](https://devblogs.microsoft.com/oldnewthing/20050726-00/?p=34803)
* [Sending a window a `WM_DESTROY` message is like prank calling somebody pretending to be the police](https://devblogs.microsoft.com/oldnewthing/20110926-00/?p=9553)
* [The secret life of `GetWindowText`](https://devblogs.microsoft.com/oldnewthing/20030821-00/?p=42833)
* [Why are the rules for `GetWindowText` so weird?](https://devblogs.microsoft.com/oldnewthing/20030904-00/?p=42663)
* [Painting only when your window is visible on the screen](https://devblogs.microsoft.com/oldnewthing/20030829-00/?p=42743)
* [Determining whether your window is covered](https://devblogs.microsoft.com/oldnewthing/20030902-00/?p=42693)
* [Obtaining a window's size and position while it is minimized](https://devblogs.microsoft.com/oldnewthing/20040707-00/?p=38523)
* [Why does calling `SetForegroundWindow` immediately followed by `GetForegroundWindow` not return the same window back?](https://devblogs.microsoft.com/oldnewthing/20161118-00/?p=94745)
* [How does Windows decide whether a newly-created window should use LTR or RTL layout?](https://devblogs.microsoft.com/oldnewthing/20220523-00/?p=106680)

### Windows Hierarchy
* [What's so special about the desktop window?](https://devblogs.microsoft.com/oldnewthing/20040224-00/?p=40493)
* [What is the window nesting limit?](https://devblogs.microsoft.com/oldnewthing/20031218-00/?p=41453)
* [What's the difference between `HWND_TOP` and `HWND_TOPMOST`?](https://devblogs.microsoft.com/oldnewthing/20051121-10/?p=33263)
* [A window can have a parent or an owner but not both](https://devblogs.microsoft.com/oldnewthing/20100315-00/?p=14613)
* [Why does my control send its notifications to the wrong window after I reparent it?](https://devblogs.microsoft.com/oldnewthing/20100316-00/?p=14593)
* [`WindowFromPoint`, `ChildWindowFromPoint`, `RealChildWindowFromPoint`, when will it all end?](https://devblogs.microsoft.com/oldnewthing/20101230-00/?p=11873)
* [`GetParent`, just as confusing as `EnumClaw`, but it's an actual function!](https://devblogs.microsoft.com/oldnewthing/20111207-00/?p=8953) (`GetAncestor()`, `GetWindow()`)
* [Having an owner window from another process is tricky, but it's sometimes the right thing to do](https://devblogs.microsoft.com/oldnewthing/20110331-00/?p=11083)
* [What is the documentation for `SetParent` trying to tell me about synchronizing the UI state?](https://devblogs.microsoft.com/oldnewthing/20171122-00/?p=97445)
* [Demonstrating what happens when a parent and child window have different UI states](https://devblogs.microsoft.com/oldnewthing/20171123-00/?p=97455)
* [Getting a parent and child window to have the same UI states](https://devblogs.microsoft.com/oldnewthing/20171124-00/?p=97456)

### Window Styles
* [Which window style bits belong to whom?](https://devblogs.microsoft.com/oldnewthing/20031203-00/?p=41633)
* [How do I indicate that I want my window to follow right-to-left layout rules?](https://devblogs.microsoft.com/oldnewthing/20100611-00/?p=13743)
* [Why isn't my transparent static control transparent?](https://devblogs.microsoft.com/oldnewthing/20111028-00/?p=9243) (`WS_EX_TRANSPARENT`)
* [Like the cake, `WS_EX_TRANSPARENT` is a lie, or at least not the entire truth](https://devblogs.microsoft.com/oldnewthing/20121217-00/?p=5823)
* [I used `WS_EX_COMPOSITED` to get rid of my redrawing flicker, but it resulted in sluggish response](https://devblogs.microsoft.com/oldnewthing/20171018-00/?p=97245)
* [How can I use `WS_CLIP­CHILDREN` and still be able to draw a control with a transparent background?](https://devblogs.microsoft.com/oldnewthing/20181005-00/?p=99905)

### Window Classes
* [What is the `HINSTANCE` passed to `CreateWindow` and `RegisterClass` used for?](https://devblogs.microsoft.com/oldnewthing/20050418-59/?p=35873)
* [Using the wrong `HINSTANCE` in `RegisterClass` is like identity theft](https://devblogs.microsoft.com/oldnewthing/20110715-00/?p=10133)
* [If the `RegisterClass` function takes ownership of the custom background brush, why is it leaking?](https://devblogs.microsoft.com/oldnewthing/20231218-00/?p=109163)
* [Changing a window class affects all windows which belong to that class](https://devblogs.microsoft.com/oldnewthing/20060227-12/?p=32133)
* [What does `CS_SAVEBITS` do?](https://devblogs.microsoft.com/oldnewthing/20060428-00/?p=31373)
* [What does the `CS_OWNDC` class style do?](https://devblogs.microsoft.com/oldnewthing/20060601-06/?p=31003)
* [What does the `CS_CLASSDC` class style do?](https://devblogs.microsoft.com/oldnewthing/20060602-00/?p=30993)
* [Modifying the `CS_NOCLOSE` style does affect all windows of the class, just not necessarily in an immediately noticeable way](https://devblogs.microsoft.com/oldnewthing/20150305-00/?p=44533)
* [Why does `PrintWindow` hate `CS_PARENTDC`? Because EVERYBODY hates `CS_PARENTDC`!](https://devblogs.microsoft.com/oldnewthing/20120604-00/?p=7463)
* [Why does `PrintWindow` hate `CS_PARENTDC`? redux](https://devblogs.microsoft.com/oldnewthing/20140410-00/?p=1283)
* [Safer subclassing](https://devblogs.microsoft.com/oldnewthing/20031111-00/?p=41883)
* [Private classes, superclassing, and global subclassing](https://devblogs.microsoft.com/oldnewthing/20100215-00/?p=14943)
* [What makes `RealGetWindowClass` so much more real than `GetClassName`?](https://devblogs.microsoft.com/oldnewthing/20101231-00/?p=11863)
* [Why does `CreateWindowEx` take the extended style parameter as its first parameter instead of its last?](https://devblogs.microsoft.com/oldnewthing/20201207-00/?p=104518)
* [When should I use `CS_GLOBALCLASS`?](https://devblogs.microsoft.com/oldnewthing/20230310-00/?p=107926)
* [How unique must the uIdSubclass parameter be when I call `Set­Window­Subclass`?](https://devblogs.microsoft.com/oldnewthing/20230323-00/?p=107962)


## Top-Level Windows

### Window Frame and Caption
* [Getting a custom right-click menu for the caption icon](https://devblogs.microsoft.com/oldnewthing/20031027-00/?p=42023)
* [Drawing an active-looking caption even when not active](https://devblogs.microsoft.com/oldnewthing/20031029-00/?p=42003)
* [How do I suppress full window drag/resize for just one window?](https://devblogs.microsoft.com/oldnewthing/20100129-01/?p=15133)
* [How do I switch a window between normal and fullscreen?](https://devblogs.microsoft.com/oldnewthing/20100412-00/?p=14353)
* [How do I enable and disable the minimize, maximize, and close buttons in my caption bar?](https://devblogs.microsoft.com/oldnewthing/20100604-00/?p=13803)
* [Getting the location of the Close button in the title bar](https://devblogs.microsoft.com/oldnewthing/20140505-00/?p=1083)
* [Getting the location of the Close button in the title bar, from Windows 2000 or Windows XP](https://devblogs.microsoft.com/oldnewthing/20140630-00/?p=623)
* [Why are the dimensions of a maximized window larger than the monitor?](https://devblogs.microsoft.com/oldnewthing/20150304-00/?p=44543)
* [Creating a window that can be resized in only one direction](https://devblogs.microsoft.com/oldnewthing/20150504-00/?p=44944)
* [Why don't you forward `WM_GETMINMAXINFO` and clamp the results?](https://devblogs.microsoft.com/oldnewthing/20150513-00/?p=45611)

### DWM
* [Why doesn't my program receive the `WM_DWMSENDICONICTHUMBNAIL` message when I ask for an iconic representation?](https://devblogs.microsoft.com/oldnewthing/20100205-00/?p=15043)
* [The `MARGINS` parameter to the `DwmExtendFrameIntoClientArea` function controls how far the frame extends into the client area](https://devblogs.microsoft.com/oldnewthing/20110113-00/?p=11763)
* [How do I suppress the default animation that occurs when I hide or show a window?](https://devblogs.microsoft.com/oldnewthing/20121003-00/?p=6423)
* [Display a custom thumbnail for your application (and while you're at it, a custom live preview)](https://devblogs.microsoft.com/oldnewthing/20130225-00/?p=5153)
* [How can I detect that my window has been suppressed from the screen by the shell?](https://devblogs.microsoft.com/oldnewthing/20200302-00/?p=103507) ("window cloaking")

### Dialogs
* [Why can't I create my dialog box? Rookie mistake #1](https://devblogs.microsoft.com/oldnewthing/?p=28123)
* [Why can't I create my dialog box? Rookie mistake #2](https://devblogs.microsoft.com/oldnewthing/20070207-04/?p=28113)
* [Returning values from a dialog procedure](https://devblogs.microsoft.com/oldnewthing/20031107-00/?p=41923)
* [A different type of dialog procedure](https://devblogs.microsoft.com/oldnewthing/20031112-00/?p=41863)
* [Another different type of dialog procedure](https://devblogs.microsoft.com/oldnewthing/20031113-00/?p=41843)
* [The default answer to every dialog box is "Cancel"](https://devblogs.microsoft.com/oldnewthing/20030901-00/?p=42723)
* [Rotating the Z-order](https://devblogs.microsoft.com/oldnewthing/20030826-00/?p=42793)
* [Using the `TAB` key to navigate in non-dialogs](https://devblogs.microsoft.com/oldnewthing/20031021-00/?p=42083)
* [Using the `TAB` key to navigate in non-dialogs, redux](https://devblogs.microsoft.com/oldnewthing/20131009-00/?p=2983)
* [Preventing edit control text from being autoselected in a dialog box](https://devblogs.microsoft.com/oldnewthing/20031114-00/?p=41823)
* [Those who do not understand the dialog manager are doomed to reimplement it, badly](https://devblogs.microsoft.com/oldnewthing/20070627-00/?p=26243)
* [Other tricks with `WM_GETDLGCODE`](https://devblogs.microsoft.com/oldnewthing/20031126-00/?p=41703)
* [`GetDialogBaseUnits` is a crock](https://devblogs.microsoft.com/oldnewthing/20040217-00/?p=40573)
* [Why isn’t `MapDialogRect` mapping dialog rectangles?](https://devblogs.microsoft.com/oldnewthing/20211021-00/?p=105818)
* [Why are dialog boxes initially created hidden?](https://devblogs.microsoft.com/oldnewthing/20040311-00/?p=40303)
* [What's the deal with the `DS_SHELLFONT` flag?](https://devblogs.microsoft.com/oldnewthing/20050204-00/?p=36523)
* [Why does `DS_SHELLFONT = DS_FIXEDSYS | DS_SETFONT`?](https://devblogs.microsoft.com/oldnewthing/20050207-00/?p=36513)
* [How to set focus in a dialog box](https://devblogs.microsoft.com/oldnewthing/20040802-00/?p=38283)
* [Never leave focus on a disabled control](https://devblogs.microsoft.com/oldnewthing/20040804-00/?p=38243)
* [A subtlety in restoring previous window position](https://devblogs.microsoft.com/oldnewthing/20050314-00/?p=36203)
* [Things you already know: How do I wait until my dialog box is displayed before doing something?](https://devblogs.microsoft.com/oldnewthing/20060922-03/?p=29623)
* [What does `TranslateAccelerator` do?](https://devblogs.microsoft.com/oldnewthing/20080523-00/?p=22203)
* [If I have a modeless dialog box with custom accelerators, which should I call first: `IsDialogMessage` or `TranslateAccelerator`](https://devblogs.microsoft.com/oldnewthing/20160818-00/?p=94115)
* [Gentle reminder: On a dialog box, do not give OK and Cancel accelerators](https://devblogs.microsoft.com/oldnewthing/20080508-00/?p=22403)
* [Why are accelerators for hidden controls still active?](https://devblogs.microsoft.com/oldnewthing/?p=22113)
* [How do I make my accelerators apply only when used in the main window and not when the user is using a modeless dialog?](https://devblogs.microsoft.com/oldnewthing/20200807-00/?p=104056)
* [Why doesn't the `TAB` key work on controls I've marked as `WS_TABSTOP`?](https://devblogs.microsoft.com/oldnewthing/20100930-00/?p=12683)
* [You can't use the `WM_USER` message in a dialog box](https://devblogs.microsoft.com/oldnewthing/20121024-00/?p=6263)
* [How can I make a dialog box right-to-left at runtime?](https://devblogs.microsoft.com/oldnewthing/20181122-00/?p=100295)
* [How does the dialog manager calculate the average width of a character?](https://devblogs.microsoft.com/oldnewthing/20221103-00/?p=107350)

### Nested and Embedded Dialogs
* [What is the `DS_CONTROL` style for?](https://devblogs.microsoft.com/oldnewthing/20040730-00/?p=38293)
* [More notes on use of the `DS_CONTROL` style](https://devblogs.microsoft.com/oldnewthing/20231101-00/?p=108952)
* [It's not a good idea to give multiple controls on a dialog box the same ID](https://devblogs.microsoft.com/oldnewthing/20120619-00/?p=7343)
* [When embedding a dialog inside another, make sure you don't accidentally create duplicate control IDs](https://devblogs.microsoft.com/oldnewthing/20120620-00/?p=7333)
* [When the default pushbutton is invoked, the invoke goes to the top-level dialog](https://devblogs.microsoft.com/oldnewthing/?p=7313)

### Common Dialogs
* [Why doesn't my `MessageBox` wrap at the right location?](https://devblogs.microsoft.com/oldnewthing/20110624-00/?p=10343)
* [How do I customize the Favorite Links section of the File Open dialog?](https://devblogs.microsoft.com/oldnewthing/20100622-00/?p=13643)
* [Why does the common file dialog change the current directory?](https://devblogs.microsoft.com/oldnewthing/20101112-00/?p=12293)
* [You can filter the Common File dialog with wildcards](https://devblogs.microsoft.com/oldnewthing/20101124-00/?p=12213)
* [How do I display the Find Printers dialog programmatically?](https://devblogs.microsoft.com/oldnewthing/20110628-00/?p=10323)
* [Why doesn't the Open Files list in the Shared Folders snap-in show all my open files?](https://devblogs.microsoft.com/oldnewthing/20110823-00/?p=9833)
* [A common control for associating extensions is well overdue](https://devblogs.microsoft.com/oldnewthing/20110914-00/?p=9653)
* [Filtering the folders that appear in the Browse for Folder dialog](https://devblogs.microsoft.com/oldnewthing/20131014-00/?p=2943)
* [Opening the classic folder browser dialog with a specific folder preselected](https://devblogs.microsoft.com/oldnewthing/20150406-00/?p=44303)
* [Why does the common file save dialog create a temporary file and then delete it?](https://devblogs.microsoft.com/oldnewthing/?p=1123)
* [Customing the standard color-picker dialog](https://devblogs.microsoft.com/oldnewthing/20140707-00/?p=563)
* [How do I set the initial directory of the File Open dialog to a virtual directory?](https://devblogs.microsoft.com/oldnewthing/20170619-00/?p=96425)
* [When I select multiple files in the File Open dialog, why does the last item come first?](https://devblogs.microsoft.com/oldnewthing/20190409-00/?p=102406)
* [I set the `OFN_NONETWORKBUTTON` option in the `OPENFILENAME` structure, but it has no effect on the network item in the navigation pane](https://devblogs.microsoft.com/oldnewthing/20190705-00/?p=102660)
* [How do I add custom controls to the common file open or file save dialogs?](https://devblogs.microsoft.com/oldnewthing/20211227-00/?p=106054)
* [How can I get my `FileSavePicker` to open in the same folder that was picked by the `FileOpenPicker` or `FolderPicker`?](https://devblogs.microsoft.com/oldnewthing/20220525-00/?p=106685) (win32/COM equivalent mentioned at the end of the post)

### Control Navigation
* [Using the `TAB` key to navigate in non-dialogs](https://devblogs.microsoft.com/oldnewthing/20031021-00/?p=42083)
* [Using the `TAB` key to navigate in non-dialogs, redux](https://devblogs.microsoft.com/oldnewthing/20131009-00/?p=2983)
* [Managing the UI state of accelerators and focus rectangles](https://devblogs.microsoft.com/oldnewthing/20050503-00/?p=35723)
* [Custom navigation in dialog boxes, redux](https://devblogs.microsoft.com/oldnewthing/20100222-00/?p=14863)
* [Dialog boxes return focus to the control that had focus when you last switched away; how do I get in on that action for my own windows?](https://devblogs.microsoft.com/oldnewthing/20140521-00/?p=943)
* [How can I create a non-circular tab order, or some other type of custom ordering in my Win32 dialog?](https://devblogs.microsoft.com/oldnewthing/20201231-00/?p=104627)

### Dialog Manager
* [The dialog manager, part 1: Warm-ups](https://devblogs.microsoft.com/oldnewthing/20050329-00/?p=36043)
* [The dialog manager, part 2: Creating the frame window](https://devblogs.microsoft.com/oldnewthing/20050330-00/?p=36023)
* [The dialog manager, part 3: Creating the controls](https://devblogs.microsoft.com/oldnewthing/20050331-00/?p=36003)
* [The dialog manager, part 4: The dialog loop](https://devblogs.microsoft.com/oldnewthing/20050401-00/?p=35993)
* [The dialog manager, part 5: Converting a non-modal dialog box to modal](https://devblogs.microsoft.com/oldnewthing/20050404-48/?p=35983)
* [The dialog manager, part 6: Subtleties in message loops](https://devblogs.microsoft.com/oldnewthing/20050405-46/?p=35973)
* [The dialog manager, part 7: More subtleties in message loops](https://devblogs.microsoft.com/oldnewthing/20050406-57/?p=35963)
* [The dialog manager, part 8: Custom navigation in dialog boxes](https://devblogs.microsoft.com/oldnewthing/20050407-00/?p=35953)
* [The dialog manager, part 9: Custom accelerators in dialog boxes](https://devblogs.microsoft.com/oldnewthing/20050408-41/?p=35943)

### Modality
* [The correct order for disabling and enabling windows](https://devblogs.microsoft.com/oldnewthing/20040227-00/?p=40463)
* [Modality, part 1: UI-modality vs code-modality](https://devblogs.microsoft.com/oldnewthing/20050218-00/?p=36413)
* [Modality, part 2: Code-modality vs UI-modality](https://devblogs.microsoft.com/oldnewthing/20050221-00/?p=36403)
* [Modality, part 3: The `WM_QUIT` message](https://devblogs.microsoft.com/oldnewthing/20050222-00/?p=36393)
* [Modality, part 4: The importance of setting the correct owner for modal UI](https://devblogs.microsoft.com/oldnewthing/20050223-00/?p=36383)
* [Modality, part 5: Setting the correct owner for modal UI](https://devblogs.microsoft.com/oldnewthing/20050224-00/?p=36373)
* [Modality, part 6: Interacting with a program that has gone modal](https://devblogs.microsoft.com/oldnewthing/20050228-00/?p=36343)
* [Modality, part 7: A timed `MessageBox`, the cheap version](https://devblogs.microsoft.com/oldnewthing/20050301-00/?p=36333)
* [Modality, part 8: A timed `MessageBox`, the better version](https://devblogs.microsoft.com/oldnewthing/20050304-00/?p=36273)
* [Modality, part 9: Setting the correct owner for modal UI, practical exam](https://devblogs.microsoft.com/oldnewthing/20110121-00/?p=11703)
* [Thread messages are eaten by modal loops](https://devblogs.microsoft.com/oldnewthing/20050426-18/?p=35783)
* [Rescuing thread messages from modal loops via message filters](https://devblogs.microsoft.com/oldnewthing/20050428-00/?p=35753)

### Property Sheets
* [What other effects does `DS_SHELLFONT` have on property sheet pages?](https://devblogs.microsoft.com/oldnewthing/20050208-00/?p=36503)
* [`PSM_ISDIALOGMESSAGE` is to modeless property sheets as `IsDialogMessage` is to modeless dialog boxes](https://devblogs.microsoft.com/oldnewthing/20100309-00/?p=14673)
* [You can extend the `PROPSHEETPAGE` structure with your own bonus data](https://devblogs.microsoft.com/oldnewthing/20110318-00/?p=11183)
* [The `PSN_SETACTIVE` notification is sent each time your wizard page is activated](https://devblogs.microsoft.com/oldnewthing/20111021-00/?p=9323)
* [Appending additional payload to a `PROPSHEETPAGE` structure](https://devblogs.microsoft.com/oldnewthing/20211124-00/?p=105961)
* [How do I pass an array of variable-sized `PROPSHEETPAGE` structures to PropertySheet?](https://devblogs.microsoft.com/oldnewthing/20211125-00/?p=105967)


## Controls

* [Just because you're a control doesn't mean that you're necessarily inside a dialog box](https://devblogs.microsoft.com/oldnewthing/20070820-00/?p=25513)

### Animation Controls
* [Limitations of the shell animation control](https://devblogs.microsoft.com/oldnewthing/20050216-00/?p=36433)
* [Why does the version 6 animation control not use a background thread?](https://devblogs.microsoft.com/oldnewthing/?p=31883)

### Buttons
* [What's the `BS_PUSHLIKE` button style for?](https://devblogs.microsoft.com/oldnewthing/20070921-00/?p=25023) (Don't use, it's completely obsolete nowadays. Use check box or radio button instead.)

### Combo Boxes
* [Speeding up adding items to a combobox or listbox](https://devblogs.microsoft.com/oldnewthing/20040610-00/?p=38933) (`WM_SETREDRAW`)

### Edit Controls
* [What's the deal with the `EM_SETHILITE` message?](https://devblogs.microsoft.com/oldnewthing/20071025-00/?p=24693)
* [Preventing edit control text from being autoselected in a dialog box](https://devblogs.microsoft.com/oldnewthing/20031114-00/?p=41823)
* [How do I suppress the `CapsLock` warning on password edit controls?](https://devblogs.microsoft.com/oldnewthing/20081010-00/?p=20603)
* [The early history of the `ES_NUMBER` edit control style](https://devblogs.microsoft.com/oldnewthing/20190220-00/?p=100975)
* [How do I allow negative numbers with the `ES_NUMBER` edit control style?](https://devblogs.microsoft.com/oldnewthing/20190221-00/?p=100985)
* [How do I permit a minus sign to be entered into my edit control, but only if it’s the first character?](https://devblogs.microsoft.com/oldnewthing/20190222-00/?p=100995)

### List Views
* [Positioned vs. non-positioned listview views](https://devblogs.microsoft.com/oldnewthing/?p=38483)
* [Displaying infotips for folded and unfolded listview items](https://devblogs.microsoft.com/oldnewthing/20061213-00/?p=28733)
* [Computing listview infotips in the background](https://devblogs.microsoft.com/oldnewthing/20061214-02/?p=28713)
* [What's the difference between `LVM_HITTEST` and `LVM_INSERTMARKHITTEST`?](https://devblogs.microsoft.com/oldnewthing/20071024-00/?p=24703)
* [Why is there an `LVN_ODSTATECHANGED` notification when there's already a perfectly good `LVN_ITEMCHANGED` notification?](https://devblogs.microsoft.com/oldnewthing/20101028-00/?p=12423)
* [Creating a listview with checkboxes on some items but not others](https://devblogs.microsoft.com/oldnewthing/20140113-00/?p=2103)
* [How can I programmatically resize a listview column to fit its contents?](https://devblogs.microsoft.com/oldnewthing/20150309-00/?p=44513)
* [How do I create a disabled checkbox for a listview item?](https://devblogs.microsoft.com/oldnewthing/20180524-00/?p=98825)
* [Speeding up adding items to a combobox or listbox](https://devblogs.microsoft.com/oldnewthing/20040610-00/?p=38933) (`WM_SETREDRAW`)

### Rich Text Controls
* ~~[The history of the RichEdit control from Murray Sargent](https://devblogs.microsoft.com/oldnewthing/20070111-20/?p=28433)~~
  (The post is just a (broken) link to [https://blogs.msdn.microsoft.com/murrays/2006/10/19/some-richedit-history/](https://blogs.msdn.microsoft.com/murrays/2006/10/19/some-richedit-history/))
* [How do I load an entire file into a rich text control?](https://devblogs.microsoft.com/oldnewthing/20070110-13/?p=28463)
* [How do I put more than 32,000 characters into a rich text control?](https://devblogs.microsoft.com/oldnewthing/20070111-02/?p=28443)
* [How do I print the contents of a rich text control?](https://devblogs.microsoft.com/oldnewthing/20070112-02/?p=28423)

### Scrollbars
* [The scratch program](https://devblogs.microsoft.com/oldnewthing/20030723-00/?p=43073)
* [Scrollbars, part 2](https://devblogs.microsoft.com/oldnewthing/20030725-00/?p=43053)
* [Scrollbars, part 3: Optimizing the paint cycle](https://devblogs.microsoft.com/oldnewthing/20030729-00/?p=43033)
* [Scrollbars, part 4: Adding a proportional scrollbar](https://devblogs.microsoft.com/oldnewthing/20030731-00/?p=43003)
* Likely part 5: [Keyboard accessibility for scrollbars](https://devblogs.microsoft.com/oldnewthing/20030805-00/?p=42983)
* Addendum to part 5: [A subtlety in the keyboard code](https://devblogs.microsoft.com/oldnewthing/20030807-00/?p=42953)
* [Scrollbars part 6 - The wheel](https://devblogs.microsoft.com/oldnewthing/20030807-00/?p=42963)
* [Scrollbars part 7 - Integrality](https://devblogs.microsoft.com/oldnewthing/20030811-00/?p=42933)
* [Scrollbars part 8 - Integral interactive resizing](https://devblogs.microsoft.com/oldnewthing/20030813-00/?p=42913)
* [Scrollbars part 9 - Maintaining the metaphor](https://devblogs.microsoft.com/oldnewthing/20030909-00/?p=42603)
* [Scrollbars part 10 - Towards a deeper understanding of the `WM_NCCALCSIZE` message](https://devblogs.microsoft.com/oldnewthing/20030911-00/?p=42553)
* [Scrollbars part 11: Towards an even deeper understanding of the `WM_NCCALCSIZE` message](https://devblogs.microsoft.com/oldnewthing/20030915-00/?p=42493)
* [Answers to exercise from Scrollbars Part 11](https://devblogs.microsoft.com/oldnewthing/20030917-00/?p=42453)
* [Scrollbars part 12: Applying `WM_NCCALCSIZE` to our scrollbar sample](https://devblogs.microsoft.com/oldnewthing/20030917-00/?p=42463)
* [Scrollbars redux: Part 12](https://devblogs.microsoft.com/oldnewthing/20031016-00/?p=42133)
* [There are two types of scrollbars](https://devblogs.microsoft.com/oldnewthing/20040510-00/?p=39413)
* [Why was `WHEEL_DELTA` chosen to be 120 instead of a much more convenient value like 100 or even 10?](https://devblogs.microsoft.com/oldnewthing/20130123-00/?p=5473)
* [Why does setting the horizontal scroll bar range for the first time also set the vertical range, and vice versa?](https://devblogs.microsoft.com/oldnewthing/20160727-00/?p=93965)
* [Autoscrolling on drag, part 1: Basic implementation](https://devblogs.microsoft.com/oldnewthing/20210125-00/?p=104757)
* [Autoscrolling on drag, part 2: Why does scrolling go faster if I wiggle the mouse?](https://devblogs.microsoft.com/oldnewthing/20210126-00/?p=104759)
* [Autoscrolling on drag, part 3: Dynamic autoscroll based on mouse position](https://devblogs.microsoft.com/oldnewthing/20210127-00/?p=104764)
* [Autoscrolling on drag, part 4: Dynamic autoscroll based on escape velocity](https://devblogs.microsoft.com/oldnewthing/20210128-00/?p=104768)
* [Autoscrolling on drag, part 5: Adding wiggle-to-scroll to escape velocity](https://devblogs.microsoft.com/oldnewthing/20210129-00/?p=104773)

### Static Controls
* [When will the static control automatically delete the image loaded into it, and when is it the responsibility of the application?](https://devblogs.microsoft.com/oldnewthing/20140219-00/?p=1713)

### Tab Controls
* [How should I create controls on my dialog box that has a tab control?](https://devblogs.microsoft.com/oldnewthing/20191015-00/?p=102996)
* [How am I supposed to create children of the Win32 tab control?](https://devblogs.microsoft.com/oldnewthing/20211110-00/?p=105889)

### Toolbars
* [Why are there both `TBSTYLE_EX_VERTICAL` and `CCS_VERT`?](https://devblogs.microsoft.com/oldnewthing/20070328-00/?p=27473)
* [How do I create a toolbar that sits in the taskbar?](https://devblogs.microsoft.com/oldnewthing/20091109-00/?p=16113)
* [How do I create a right-aligned toolbar button?](https://devblogs.microsoft.com/oldnewthing/20110616-00/?p=10413)
* [Creating custom tasks on a jump list](https://devblogs.microsoft.com/oldnewthing/20131223-00/?p=2303)

### Tooltips
* [Coding in-place tooltips](https://devblogs.microsoft.com/oldnewthing/20060626-11/?p=30743)
* [Using custom-draw in tooltips to adjust the font](https://devblogs.microsoft.com/oldnewthing/20060627-22/?p=30723)
* [Multiplexing multiple tools into one in a tooltip](https://devblogs.microsoft.com/oldnewthing/20060628-05/?p=30703)
* [Generating tooltip text dynamically](https://devblogs.microsoft.com/oldnewthing/20060629-00/?p=30693)
* [Why can't I display a tooltip for a disabled window?](https://devblogs.microsoft.com/oldnewthing/20070405-00/?p=27363)
* [Over-documenting `TTM_RELAYEVENT` and why it results in a one-second periodic timer running as long as the tooltip is visible](https://devblogs.microsoft.com/oldnewthing/20200110-00/?p=103316)

### Trackbars
* [Adding a `Ctrl`+arrow accelerator for moving the trackbar by just one unit, part 1: Initial plunge](https://devblogs.microsoft.com/oldnewthing/20181023-00/?p=100035)
* [Adding a `Ctrl`+arrow accelerator for moving the trackbar by just one unit, part 2: Second try](https://devblogs.microsoft.com/oldnewthing/20181024-00/?p=100045)
* [How do I prevent users from using the mouse to drag the trackbar thumb to positions that aren’t multiples of five? Part 1: Reframe the problem](https://devblogs.microsoft.com/oldnewthing/20181025-00/?p=100055)
* [How do I prevent users from using the mouse to drag the trackbar thumb to positions that aren’t multiples of five? Part 2: Nudging the thumb position](https://devblogs.microsoft.com/oldnewthing/20181026-00/?p=100065)

### Tree-List Views
* [The `TVS_CHECKBOXES` style is quirky, which is a polite way of saying that it is crazy](https://devblogs.microsoft.com/oldnewthing/20171127-00/?p=97465)
* [Beware of the leaked image list when using the `TVS_CHECKBOXES` style](https://devblogs.microsoft.com/oldnewthing/20171128-00/?p=97475)
* [Creating tree view check boxes manually: A simple state image list](https://devblogs.microsoft.com/oldnewthing/20171129-00/?p=97485)
* [Creating tree view check boxes manually: Responding to clicks](https://devblogs.microsoft.com/oldnewthing/20171130-00/?p=97495)
* [Creating tree view check boxes manually: Themed check boxes](https://devblogs.microsoft.com/oldnewthing/20171201-00/?p=97505)
* [Tree view check boxes: A sordid history](https://devblogs.microsoft.com/oldnewthing/20171204-00/?p=97515)
* [Tree view check boxes: The extended check box states](https://devblogs.microsoft.com/oldnewthing/20171205-00/?p=97525)


## Processing of Messages

* [Which message numbers belong to whom?](https://devblogs.microsoft.com/oldnewthing/20031202-00/?p=41653)
* [The various ways of sending a message](https://devblogs.microsoft.com/oldnewthing/20041119-00/?p=37243)
* [Broadcasting user-defined messages](https://devblogs.microsoft.com/oldnewthing/20040505-00/?p=39503)
* [When can a thread receive window messages?](https://devblogs.microsoft.com/oldnewthing/20040608-00/?p=38983)
* [What's the difference between `GetKeyState` and `GetAsyncKeyState`?](https://devblogs.microsoft.com/oldnewthing/20041130-00/?p=37173)
* [Thread messages are eaten by modal loops](https://devblogs.microsoft.com/oldnewthing/20050426-18/?p=35783)
* [Rescuing thread messages from modal loops via message filters](https://devblogs.microsoft.com/oldnewthing/20050428-00/?p=35753)
* [The dangers of filtering window messages](https://devblogs.microsoft.com/oldnewthing/20050209-00/?p=36493)
* [You can't simulate keyboard input with `PostMessage`](https://devblogs.microsoft.com/oldnewthing/20050530-11/?p=35513)
* [Pumping messages while waiting for a period of time](https://devblogs.microsoft.com/oldnewthing/20060126-00/?p=32513)
* [In pursuit of the message queue](https://devblogs.microsoft.com/oldnewthing/20060221-09/?p=32203)
* [No, really, you need to pass all unhandled messages to `DefWindowProc`](https://devblogs.microsoft.com/oldnewthing/20060425-16/?p=31413)
* [Even if you have code to handle a message, you're allowed to call `DefWindowProc`, because you were doing that anyway after all](https://devblogs.microsoft.com/oldnewthing/20090105-00/?p=19603)
* [What were `Get/SetMessageExtraInfo` ever used for?](https://devblogs.microsoft.com/oldnewthing/20101129-00/?p=12173)
* [Why is `GetWindowLongPtr` returning a garbage value on 64-bit Windows?](https://devblogs.microsoft.com/oldnewthing/20131226-00/?p=2263)
* [`TrackMouseEvent` tracks mouse events in your window, but only if the events belong to your window](https://devblogs.microsoft.com/oldnewthing/20101206-00/?p=12113)
* [Don't forget to include the message queue in your lock hierarchy](https://devblogs.microsoft.com/oldnewthing/20110418-00/?p=10913)
* [What happens to a sent message when `SendMessageTimeout` reaches its timeout?](https://devblogs.microsoft.com/oldnewthing/20110915-00/?p=9643)
* [Why can't I `PostMessage` the `WM_COPYDATA` message, but I can `SendMessageTimeout` it with a tiny timeout?](https://devblogs.microsoft.com/oldnewthing/20110916-00/?p=9623)
* [Even though mouse-move, paint, and timer messages are generated on demand, it's still possible for one to end up in your queue](https://devblogs.microsoft.com/oldnewthing/20130523-00/?p=4273)
* [Posted messages are processed ahead of input messages, even if they were posted later](https://devblogs.microsoft.com/oldnewthing/20130531-00/?p=4203)
* [What kind of messages can a message-only window receive?](https://devblogs.microsoft.com/oldnewthing/20171218-00/?p=97595)
* [If the prototypes of `DispatchMessageA` and `DispatchMessageW` are identical, why have both?](https://devblogs.microsoft.com/oldnewthing/20181101-00/?p=100105)
* [Those who do not understand the dialog manager are doomed to reimplement it, badly](https://devblogs.microsoft.com/oldnewthing/20070627-00/?p=26243)
* [How can I trigger a recalc of the mouse cursor after I changed some of my internal application state?](https://devblogs.microsoft.com/oldnewthing/20220921-00/?p=107203)
* [How can I trigger a recalc of the mouse cursor after I changed some of my internal application state?, follow-up](https://devblogs.microsoft.com/oldnewthing/20230525-00/?p=108247)
* [`GetQueueStatus` and the queue state](https://devblogs.microsoft.com/oldnewthing/20230925-00/?p=108820)

### Hooking
* [What is the `HINSTANCE` passed to `SetWindowsHookEx` used for?](https://devblogs.microsoft.com/oldnewthing/20050425-41/?p=35803)
* [How can I get notified when the cursor changes?](https://devblogs.microsoft.com/oldnewthing/20151116-00/?p=92091)
* [What does the thread parameter to `Set­Windows­Hook­Ex` actually mean?](https://devblogs.microsoft.com/oldnewthing/20180926-00/?p=99825)
* [Why does `SetFocus` fail without telling me why?](https://devblogs.microsoft.com/oldnewthing/20190614-00/?p=102593)


## Specific Messages

### Notifications
* [What's the difference between the `wParam` of the `WM_NOTIFY` message and the `idFrom` in the `NMHDR` structure.](https://devblogs.microsoft.com/oldnewthing/20131204-00/?p=2463)
* [Restating the obvious about the `WM_COMMAND` message](https://devblogs.microsoft.com/oldnewthing/20060302-10/?p=32093)
* [Restating the obvious about the `WM_NOTIFY` message](https://devblogs.microsoft.com/oldnewthing/20090821-00/?p=17033)

### Window Construction and Destruction
* [What is the difference between `WM_DESTROY` and `WM_NCDESTROY`?](https://devblogs.microsoft.com/oldnewthing/20050726-00/?p=34803)
* [How can I determine the reason why my window is closing?](https://devblogs.microsoft.com/oldnewthing/20190411-00/?p=102411) (`WM_CLOSE`)

### Window Geometry Messages
* [Use `WM_WINDOWPOSCHANGED` to react to window state changes](https://devblogs.microsoft.com/oldnewthing/20080115-00/?p=23813)
* [Use `WM_WINDOWPOSCHANGING` to intercept window state changes](https://devblogs.microsoft.com/oldnewthing/20080116-00/?p=23803)

### Window Painting Messages
* [Paint messages will come in as fast as you let them](https://devblogs.microsoft.com/oldnewthing/20111219-00/?p=8863) (`WM_PAINT`)
* [What happens if I don't paint when I get a `WM_PAINT` message?](https://devblogs.microsoft.com/oldnewthing/20141203-00/?p=43483)
* [What is the implementation of `WM_PRINTCLIENT`?](https://devblogs.microsoft.com/oldnewthing/20090330-00/?p=18683)
* [There's a default implementation for `WM_SETREDRAW`, but you might be able to do better](https://devblogs.microsoft.com/oldnewthing/20110124-00/?p=11683)
* [Speeding up adding items to a combobox or listbox](https://devblogs.microsoft.com/oldnewthing/20040610-00/?p=38933) (`WM_SETREDRAW`)
* [Using `WM_SETREDRAW` to speed up adding a lot of elements to a control](https://devblogs.microsoft.com/oldnewthing/20140407-00/?p=1313)

### Window Focus Messages
* [`WM_KILLFOCUS` is the wrong time to do field validation](https://devblogs.microsoft.com/oldnewthing/20040419-00/?p=39753)
* [The dangers of playing focus games when handling a `WM_KILLFOCUS` message](https://devblogs.microsoft.com/oldnewthing/20050808-16/?p=34673)
* [Why doesn't the `MoveWindow` function generate the `WM_GETMINMAXINFO` message?](https://devblogs.microsoft.com/oldnewthing/20090309-00/?p=18903)

### Keyboard Messages
* [How do I respond to the `WM_MENUCHAR` message?](https://devblogs.microsoft.com/oldnewthing/20171208-00/?p=97545)

### Mouse Messages
* [Why is there no `WM_MOUSEENTER` message?](https://devblogs.microsoft.com/oldnewthing/20031013-00/?p=42193)
* [Why do I get spurious `WM_MOUSEMOVE` messages?](https://devblogs.microsoft.com/oldnewthing/20031001-00/?p=42343)
* [Sure, I can get spurious `WM_MOUSEMOVE` messages, but why do they keep streaming in?](https://devblogs.microsoft.com/oldnewthing/20090617-00/?p=17863)
* [How do I get mouse messages faster than `WM_MOUSEMOVE`?](https://devblogs.microsoft.com/oldnewthing/20120314-00/?p=8103)
* [Logical consequences of the way Windows converts single-clicks into double-clicks](https://devblogs.microsoft.com/oldnewthing/20041015-00/?p=37553)
* [Implementing higher-order clicks](https://devblogs.microsoft.com/oldnewthing/20041018-00/?p=37543)
* [How slow do you have to slow-double-click for it to be a rename?](https://devblogs.microsoft.com/oldnewthing/20081110-00/?p=20263)
* [How can I prevent the mouse from moving in response to touch input?](https://devblogs.microsoft.com/oldnewthing/20210728-00/?p=105487)

### Dialog Messages
* [Those who do not understand the dialog manager are doomed to reimplement it, badly](https://devblogs.microsoft.com/oldnewthing/20070627-00/?p=26243)
* [Managing the UI state of accelerators and focus rectangles](https://devblogs.microsoft.com/oldnewthing/20050503-00/?p=35723) (`WM_CHANGEUISTATE`, `WM_QUERYUISTATE` and `WM_UPDATEUISTATE`)
* [Untangling the confusingly-named `WM_UPDATEUISTATE` and `WM_CHANGEUISTATE` messages](https://devblogs.microsoft.com/oldnewthing/20130516-00/?p=4343)
* [Who sends the initial `WM_UPDATEUISTATE` message?](https://devblogs.microsoft.com/oldnewthing/20130517-00/?p=4323)
* [How can I prevent the keyboard focus rectangle from appearing on a control I created?](https://devblogs.microsoft.com/oldnewthing/20171206-00/?p=97526)
* [Other tricks with `WM_GETDLGCODE`](https://devblogs.microsoft.com/oldnewthing/20031126-00/?p=41703)
* [How do I prevent multi-line edit controls from eating the Enter key?](https://devblogs.microsoft.com/oldnewthing/20061012-06/?p=29413)
* [Why do `DLGC_WANTALLKEYS` and `DLGC_WANTMESSAGE` have the same value?](https://devblogs.microsoft.com/oldnewthing/20070626-00/?p=26263)

### Other Window Messages
* [The dangers of messing with activation when handling a `WM_ACTIVATE` message](https://devblogs.microsoft.com/oldnewthing/20050809-13/?p=34653)
* [Why does my window get a `WM_ACTIVATE` message when it isn't active?](https://devblogs.microsoft.com/oldnewthing/20131016-00/?p=2913)
* [A timed context menu](https://devblogs.microsoft.com/oldnewthing/20050307-00/?p=36263) (`WM_CANCELMODE`)
* [Pitfalls in handling the `WM_CONTEXTMENU` message](https://devblogs.microsoft.com/oldnewthing/20040921-00/?p=37813) (`WM_CONTEXTMENU`)
* [`WM_NCHITTEST` is for hit-testing, and hit-testing can happen for reasons other than the mouse being over your window](https://devblogs.microsoft.com/oldnewthing/20110218-00/?p=11453)
* [How likely is it that a window will receive a `WM_NULL` message out of the blue?](https://devblogs.microsoft.com/oldnewthing/20170602-00/?p=96266) (`WM_NULL`)
* [Why is there a special `PostQuitMessage` function?](https://devblogs.microsoft.com/oldnewthing/20051104-33/?p=33453) (`WM_QUIT`)
* [How does `PostQuitMessage` know which thread to post the quit message to?](https://devblogs.microsoft.com/oldnewthing/20090112-00/?p=19533) (`WM_QUIT`)
* [Who is responsible for destroying the font passed in the `WM_SETFONT` message?](https://devblogs.microsoft.com/oldnewthing/20080912-00/?p=20893) (`WM_SETFONT`)
* [When I send a `WM_GETFONT` message to a window, why don't I get a font?](https://devblogs.microsoft.com/oldnewthing/20140724-00/?p=413) (`WM_GETFONT`)
* [If my `WM_TIMER` handler takes longer than the timer period, will my queue fill up with `WM_TIMER` messages?](https://devblogs.microsoft.com/oldnewthing/20141204-00/?p=43473)
* [Killing a window timer prevents the `WM_TIMER` message from being generated for that timer, but it doesn't retroactively remove ones that were already generated](https://devblogs.microsoft.com/oldnewthing/20141205-00/?p=43463)

### System Messages
* [If one program blocks shutdown, then *all* programs block shutdown](https://devblogs.microsoft.com/oldnewthing/20200414-00/?p=103671) (`WM_QUERY­END­SESSION`, `WM_END­SESSION`)
* [Why do I have to return this goofy value for `WM_DEVICECHANGE`?](https://devblogs.microsoft.com/oldnewthing/20031205-00/?p=41613) (`WM_DEVICECHANGE`)
* [Windows doesn't close windows when a user logs off; that's your call](https://devblogs.microsoft.com/oldnewthing/20080421-00/?p=22663) (`WM_ENDSESSION`)
* [Once you return from the `WM_ENDSESSION` message, your process can be terminated at any time](https://devblogs.microsoft.com/oldnewthing/20130627-00/?p=3973) (`WM_ENDSESSION`)


## GDI

* [Why are `RECT`s endpoint-exclusive?](https://devblogs.microsoft.com/oldnewthing/20040218-00/?p=40563)
* [Can you create an information context for the display?](https://devblogs.microsoft.com/oldnewthing/20090914-00/?p=16733)
* [What does the `CS_OWNDC` class style do?](https://devblogs.microsoft.com/oldnewthing/20060601-06/?p=31003)
* [What does the `CS_CLASSDC` class style do?](https://devblogs.microsoft.com/oldnewthing/20060602-00/?p=30993)
* [How do you detect "Large Fonts"?](https://devblogs.microsoft.com/oldnewthing/20040714-00/?p=38443) (DPI)
* [Drawing a monochrome bitmap with transparency](https://devblogs.microsoft.com/oldnewthing/20050803-16/?p=34733)
* [Let GDI do your RLE compression for you](https://devblogs.microsoft.com/oldnewthing/20090408-00/?p=18603)
* [The mysterious stock bitmap: There's no way to summon it, but it shows up in various places](https://devblogs.microsoft.com/oldnewthing/20100416-00/?p=14313)
* [Why is my icon being drawn at the wrong size when I call `DrawIcon`?](https://devblogs.microsoft.com/oldnewthing/20100729-00/?p=13293)
* [You must flush GDI operations when switching between direct access and GDI access, and direct access includes other parts of GDI](https://devblogs.microsoft.com/oldnewthing/20100923-00/?p=12773)
* [How do I get the dimensions of a cursor or icon?](https://devblogs.microsoft.com/oldnewthing/20101020-00/?p=12493)
* [What are the dire consequences of not selecting objects out of my DC?](https://devblogs.microsoft.com/oldnewthing/20130306-00/?p=5043)
* [Of what use is the `RDW_INTERNALPAINT` flag?](https://devblogs.microsoft.com/oldnewthing/20130621-00/?p=4023)
* [Functions that return GDI regions rarely actually return regions](https://devblogs.microsoft.com/oldnewthing/20140327-00/?p=1383)
* [Color-aware ClearType requires access to fixed background pixels, which is a problem if you don't know what the background pixels are, or if they aren't fixed](https://devblogs.microsoft.com/oldnewthing/20150129-00/?p=44803)
* [What is the correct way of using `SaveDC` and `RestoreDC`?](https://devblogs.microsoft.com/oldnewthing/20170920-00/?p=97055)
* [How are `BitBlt` raster opcodes calculated?](https://devblogs.microsoft.com/oldnewthing/20180528-00/?p=98845)
* [Notes on `DrawText` and tab stops](https://devblogs.microsoft.com/oldnewthing/20181010-00/?p=99935)
* [Why doesn’t `GetTextExtentPoint` return the correct extent for strings containing tabs?](https://devblogs.microsoft.com/oldnewthing/20181012-00/?p=99955)
* [Why are there trivial functions like `Copy­Rect` and `Equal­Rect`?](https://devblogs.microsoft.com/oldnewthing/20200224-00/?p=103472)
* [More on trivial functions like `CopyRect` and `EqualRect`](https://devblogs.microsoft.com/oldnewthing/20200901-00/?p=104147)
* [What are the consequences of increasing the per-process GDI handle limit?](https://devblogs.microsoft.com/oldnewthing/20210831-00/?p=105624)
* [The focus rectangle says, “I’m not orange. I’m just drawn that way.”](https://devblogs.microsoft.com/oldnewthing/20211102-00/?p=105866)

### Cursors
* [The effect of `SetCursor` lasts only until the next `SetCursor`](https://devblogs.microsoft.com/oldnewthing/20050525-27/?p=35543)
* [What can or should I do with the cursor handle returned by `SetCursor`?](https://devblogs.microsoft.com/oldnewthing/20221026-00/?p=107325)
* [What is the deal with the `SM_CXCURSOR` system metric?](https://devblogs.microsoft.com/oldnewthing/20210819-00/?p=105572)
* [How do I find out the size of the mouse cursor?](https://devblogs.microsoft.com/oldnewthing/20210820-00/?p=105593)

### Brushes
* [The hollow brush](https://devblogs.microsoft.com/oldnewthing/20040126-00/?p=40903)
* [Other uses for bitmap brushes](https://devblogs.microsoft.com/oldnewthing/20031009-00/?p=42213)
* [What is the DC brush good for?](https://devblogs.microsoft.com/oldnewthing/20050420-28/?p=35843)
* [I know I can change the color of the DC pen, but what about the other attributes?](https://devblogs.microsoft.com/oldnewthing/20210721-00/?p=105467)
* [How can I extract the color from a solid color GDI brush?](https://devblogs.microsoft.com/oldnewthing/20190802-00/?p=102747)

### Pens
* [Is there a difference between creating a null pen with `Create­Pen` and just using the stock null pen?](https://devblogs.microsoft.com/oldnewthing/20200127-00/?p=103368)

### Bitmaps
* [How do I set the alpha channel of a GDI bitmap to 255?](https://devblogs.microsoft.com/oldnewthing/20210915-00/?p=105687)

### DIB
* [A survey of the various ways of creating GDI bitmaps with predefined data](https://devblogs.microsoft.com/oldnewthing/20170331-00/?p=95875)
* [Blitting between color and monochrome DCs](https://devblogs.microsoft.com/oldnewthing/20061114-01/?p=29013)
* [Manipulating the DIB color table for fun and profit](https://devblogs.microsoft.com/oldnewthing/20061115-01/?p=28993)
* [Using DIB sections to perform bulk color mapping](https://devblogs.microsoft.com/oldnewthing/?p=28983)
* [The fun and profit of manipulating the DIB color table can be done without having to modify it](https://devblogs.microsoft.com/oldnewthing/20090714-00/?p=17503)
* [Separating the metadata from the DIB pixels: Precalculating the `BITMAPINFO`](https://devblogs.microsoft.com/oldnewthing/20090715-00/?p=17483)
* [Separating the metadata from the DIB pixels: Changing the raster operation](https://devblogs.microsoft.com/oldnewthing/20090716-00/?p=17463)
* [The disembodiment of DIBs from the DIB section](https://devblogs.microsoft.com/oldnewthing/20090717-00/?p=17443)
* [What is the `hSection` parameter to `CreateDIBSection` for?](https://devblogs.microsoft.com/oldnewthing/20100108-00/?p=15343)

### `LockWindowUpdate()`
* [What does `LockWindowUpdate` do?](https://devblogs.microsoft.com/oldnewthing/20070219-00/?p=27963)
* [How is `LockWindowUpdate` meant to be used?](https://devblogs.microsoft.com/oldnewthing/20070220-07/?p=27953)
* [With what operations is `LockWindowUpdate` meant to be used?](https://devblogs.microsoft.com/oldnewthing/20070221-11/?p=27933)
* [With what operations is `LockWindowUpdate` not meant to be used?](https://devblogs.microsoft.com/oldnewthing/20070222-01/?p=27913)
* [Final remarks on `LockWindowUpdate`](https://devblogs.microsoft.com/oldnewthing/20070223-00/?p=27893)

### Painting Standard Elements
* [Rendering standard Windows elements](https://devblogs.microsoft.com/oldnewthing/20050801-11/?p=34763)
* [Rendering menu glyphs is slightly trickier](https://devblogs.microsoft.com/oldnewthing/20050802-13/?p=34743)
* [What states are possible in a `DRAWITEMSTRUCT` structure?](https://devblogs.microsoft.com/oldnewthing/20141211-00/?p=43423)

### `UXTHEME.DLL`
* [`BeginBufferedPaint`: It's not just for buffered painting any more](https://devblogs.microsoft.com/oldnewthing/20110520-00/?p=10613)
* [How do `IsThemeActive`, `IsAppThemed`, and `IsCompositionActive` differ?](https://devblogs.microsoft.com/oldnewthing/20110526-00/?p=10563)
* [How do I get the tabbed dialog effect on my own custom tabbed dialog?](https://devblogs.microsoft.com/oldnewthing/20121105-00/?p=6173)
* [How do I revert a control back to its default theme?](https://devblogs.microsoft.com/oldnewthing/20181115-00/?p=100225)

### Multiple Monitors
* [For better performance, set all your monitors to the same color format](https://devblogs.microsoft.com/oldnewthing/20100208-00/?p=15023)
* [How do I get a handle to the primary monitor?](https://devblogs.microsoft.com/oldnewthing/20070809-00/?p=25643)
* [Why does the primary monitor have `(0,0)` as its upper left coordinate?](https://devblogs.microsoft.com/oldnewthing/20100820-00/?p=13093)
* [How do I get the color depth of the screen?](https://devblogs.microsoft.com/oldnewthing/20101013-00/?p=12543)
* [How does the window manager adjust `ptMaxSize` and `ptMaxPosition` for multiple monitors?](https://devblogs.microsoft.com/oldnewthing/20150501-00/?p=44964)


## Accessibility

* [Accessibility is not just for people with disabilities](https://devblogs.microsoft.com/oldnewthing/?p=30093)
* [How to retrieve text under the cursor (mouse pointer)](https://devblogs.microsoft.com/oldnewthing/20130408-00/?p=4733)
* [How do I set an accessible name on an unlabeled control?](https://devblogs.microsoft.com/oldnewthing/20111013-00/?p=9393)
* [How can I get notified when some other window is destroyed?](https://devblogs.microsoft.com/oldnewthing/20111026-00/?p=9263)
* [Using accessibility to monitor windows as they come and go](https://devblogs.microsoft.com/oldnewthing/20130325-00/?p=4863)
* [How can I write a program that monitors another window for a title change?](https://devblogs.microsoft.com/oldnewthing/20180601-00/?p=98895)
* [How can I write a program that monitors another window for a change in size or position?](https://devblogs.microsoft.com/oldnewthing/20210104-00/?p=104656)


## COM

### Declaring COM Interfaces
* [The macros for declaring COM interfaces, revisited: C version](https://devblogs.microsoft.com/oldnewthing/20200909-00/?p=104198)
* [The macros for declaring COM interfaces, revisited: C++ version](https://devblogs.microsoft.com/oldnewthing/20200910-00/?p=104203)
* [The macros for declaring COM interfaces, revisited: C++ implementation](https://devblogs.microsoft.com/oldnewthing/20200911-00/?p=104205)
* [The oracle always tells the truth, even when it is wrong: COM method calls with a user-defined type as a return value](https://devblogs.microsoft.com/oldnewthing/20220113-00/?p=106152) (on problems of COM interfaces called from C code)
* [The COM interface contract rules exist for a reason](https://devblogs.microsoft.com/oldnewthing/20051101-54/?p=33533)
* [Giving a single object multiple COM identities, part 1](https://devblogs.microsoft.com/oldnewthing/20211026-00/?p=105834)
* [Giving a single object multiple COM identities, part 2](https://devblogs.microsoft.com/oldnewthing/20211027-00/?p=105838)
* [Giving a single object multiple COM identities, part 3](https://devblogs.microsoft.com/oldnewthing/20211028-00/?p=105852)
* [Giving a single object multiple COM identities, part 4](https://devblogs.microsoft.com/oldnewthing/20211029-00/?p=105859)
* [How do I consume raw COM interfaces from a Windows Runtime metadata file?](https://devblogs.microsoft.com/oldnewthing/20220908-00/?p=107137)


### COM Apartments
* [The dreaded "main" threading model](https://devblogs.microsoft.com/oldnewthing/20040602-00/?p=39053)
* [A slightly less brief introduction to COM apartments (but it’s still brief)](https://devblogs.microsoft.com/oldnewthing/20191125-00/?p=103135)
* [Yo dawg, I hear you like COM apartments, so I put a COM apartment in your COM apartment so you can COM apartment while you COM apartment](https://devblogs.microsoft.com/oldnewthing/20191126-00/?p=103140)
* [What kind of apartment is the private apartment I created via `CLSID_Context­Switcher`?](https://devblogs.microsoft.com/oldnewthing/20200422-00/?p=103694)
* [Setting up private COM contexts to allow yourself to unload cleanly](https://devblogs.microsoft.com/oldnewthing/20191127-00/?p=103153)
* [How do you get into a context via `IContext­Callback::Context­Callback`?](https://devblogs.microsoft.com/oldnewthing/20191128-00/?p=103157)
* [Using contexts to return to a COM apartment later](https://devblogs.microsoft.com/oldnewthing/20191129-00/?p=103162)
* [What do the output values from `CoGetApartmentType` mean?](https://devblogs.microsoft.com/oldnewthing/20180208-00/?p=97986)
* [User interface code + multi-threaded apartment = death](https://devblogs.microsoft.com/oldnewthing/?p=22603)
* [Other problems traced to violating COM single-threaded apartment rules in the shell](https://devblogs.microsoft.com/oldnewthing/20071019-00/?p=24733)
* [What’s the point of `APTTYPE_CURRENT`? I mean, of course I’m current.](https://devblogs.microsoft.com/oldnewthing/20201105-00/?p=104422)
* [How do I get a foothold in the neutral apartment?](https://devblogs.microsoft.com/oldnewthing/20210205-00/?p=104801)
* [What is so special about the Application STA?](https://devblogs.microsoft.com/oldnewthing/20210224-00/?p=104901)
* [What does it mean when a call fails with `0x8000001F = RO_E_BLOCKED_CROSS_ASTA_CALL`?](https://devblogs.microsoft.com/oldnewthing/20210225-00/?p=104908)

### COM Initialization
* [What does the `COINIT_SPEED_OVER_MEMORY` flag to `CoInitializeEx` do?](https://devblogs.microsoft.com/oldnewthing/20121108-00/?p=6143)
* [Crashing in COM after I call `CoUninitialize`, how can COM be running after it is uninitalized?](https://devblogs.microsoft.com/oldnewthing/20200129-00/?p=103380)

### COM Static Store
* [The COM static store, part 1: Introduction](https://devblogs.microsoft.com/oldnewthing/20210208-00/?p=104812)
* [The COM static store, part 2: Race conditions in setting a singleton](https://devblogs.microsoft.com/oldnewthing/20210209-00/?p=104835)
* [The COM static store, part 3: Avoiding creation of an expensive temporary when setting a singleton](https://devblogs.microsoft.com/oldnewthing/20210210-06/?p=104839)
* [The COM static store, part 4: Aggregating into a single object](https://devblogs.microsoft.com/oldnewthing/20210211-00/?p=104845)
* [The COM static store, part 5: Using COM weak references](https://devblogs.microsoft.com/oldnewthing/20210212-00/?p=104847)
* [The COM static store, part 6: Using C++ weak references](https://devblogs.microsoft.com/oldnewthing/20210215-00/?p=104865)

### COM Marshaling
* [What is COM marshaling and how do I use it?](https://devblogs.microsoft.com/oldnewthing/20151020-00/?p=91321)
* [On proper handling of buffers in COM and RPC methods](https://devblogs.microsoft.com/oldnewthing/20210715-00/?p=105446)
* [What are the rules for `CoMarshalInterThreadInterfaceInStream` and `CoGetInterfaceAndReleaseStream`?](https://devblogs.microsoft.com/oldnewthing/20151021-00/?p=91311)
* [What are the rules for `CoMarshalInterface` and `CoUnmarshalInterface`?](https://devblogs.microsoft.com/oldnewthing/20151022-00/?p=91301)
* [`CoGetInterfaceAndReleaseStream` does not mix with smart pointers](https://devblogs.microsoft.com/oldnewthing/20151023-00/?p=91291)
* [The COM marshaller uses the COM task allocator to allocate and free memory](https://devblogs.microsoft.com/oldnewthing/20090923-00/?p=16613)
* [Why do I get a `QueryInterface(IID_IMarshal)` and then nothing?](https://devblogs.microsoft.com/oldnewthing/20040220-00/?p=40533)
* [We batched up our COM requests and return a single stream of results, but the performance is still slow](https://devblogs.microsoft.com/oldnewthing/20160212-00/?p=93013)
* [What are the various usage patterns for manually-marshaled interfaces?](https://devblogs.microsoft.com/oldnewthing/20220614-00/?p=106750)
* [An initial look at the mechanics of how COM marshaling is performed](https://devblogs.microsoft.com/oldnewthing/20220615-00/?p=106753)
* [https://devblogs.microsoft.com/oldnewthing/20220616-00/?p=106757](https://devblogs.microsoft.com/oldnewthing/20220616-00/?p=106757)
* [Writing a marshal-by-value marshaler, part 1](https://devblogs.microsoft.com/oldnewthing/20220617-41/?p=106760)
* [Writing a marshal-by-value marshaler, part 2](https://devblogs.microsoft.com/oldnewthing/20220623-00/?p=106778)
* [Writing a compound marshaler](https://devblogs.microsoft.com/oldnewthing/20220621-00/?p=106767)
* [Understanding the marshaling flags: The free-threaded marshaler](https://devblogs.microsoft.com/oldnewthing/20220622-00/?p=106774)

### COM Error Handling
* [What happens to my COM server-side object when clients die unexpectedly?](https://devblogs.microsoft.com/oldnewthing/20140409-00/?p=1293)
* [Why does COM require output pointers to be initialized even on failure?](https://devblogs.microsoft.com/oldnewthing/20091231-00/?p=15463)
* [How do I convert an `HRESULT` to a Win32 error code?](https://devblogs.microsoft.com/oldnewthing/20061103-07/?p=29133)
* [How can I tell the WIL `RETURN_IF_FAILED` macro that some errors are ignorable?](https://devblogs.microsoft.com/oldnewthing/20220414-00/?p=106483)
* [Do not overload the `E_NOINTERFACE` error](https://devblogs.microsoft.com/oldnewthing/20061208-00/?p=28783)
* [What does it mean when a call fails with `0x8000001F = RO_E_BLOCKED_CROSS_ASTA_CALL`?](https://devblogs.microsoft.com/oldnewthing/20210225-00/?p=104908)
* [What does it mean when my cross-thread COM call fails with `RPC_E_SYS_CALL_FAILED`?
](https://devblogs.microsoft.com/oldnewthing/20230216-00/?p=107836)
* [Understanding a mysterious `RPC_E_WRONG­THREAD` exception when we’re on the right thread](https://devblogs.microsoft.com/oldnewthing/20230224-37/?p=107870)

### COM Asynchronous Interfaces
* [COM asynchronous interfaces, part 1: The basic pattern](https://devblogs.microsoft.com/oldnewthing/20220214-44/?p=106251)
* [COM asynchronous interfaces, part 2: Abandoning the operation](https://devblogs.microsoft.com/oldnewthing/20220215-00/?p=106253)
* [COM asynchronous interfaces, part 3: Abandoning the operation after a timeout](https://devblogs.microsoft.com/oldnewthing/20220216-00/?p=106261)
* [COM asynchronous interfaces, part 4: Doing work while waiting for the asynchronous operation](https://devblogs.microsoft.com/oldnewthing/20220217-00/?p=106263)
* [COM asynchronous interfaces, part 5: The unreliable server](https://devblogs.microsoft.com/oldnewthing/20220218-00/?p=106272)
* [COM asynchronous interfaces, part 6: Learning about completion without polling](https://devblogs.microsoft.com/oldnewthing/20220221-42/?p=106275)
* [COM asynchronous interfaces, part 7: Being called directly when the operation completes](https://devblogs.microsoft.com/oldnewthing/20220222-00/?p=106279)
* [COM asynchronous interfaces, part 8: Asynchronous release, the problems](https://devblogs.microsoft.com/oldnewthing/20220223-00/?p=106282)
* [COM asynchronous interfaces, part 9: Asynchronous release, assembling a solution](https://devblogs.microsoft.com/oldnewthing/20220224-00/?p=106288)

### GUIDs
* [What's the difference between `UuidFromString`, `IIDFromString`, `CLSIDFromString`, `GUIDFromString`...](https://devblogs.microsoft.com/oldnewthing/20151015-00/?p=91351)
* [What is the difference between `UuidToString`, `StringFromCLSID`, `StringFromIID`, and `StringFromGUID2`?](https://devblogs.microsoft.com/oldnewthing/20231113-00/?p=109011)
* [Why are there four functions for parsing strings into GUIDs, and why are they in three different DLLs?](https://devblogs.microsoft.com/oldnewthing/20160331-00/?p=93231)
* [Why does COM express GUIDs in a mix of big-endian and little-endian? Why can’t it just pick a side and stick with it?](https://devblogs.microsoft.com/oldnewthing/20220928-00/?p=107221)

### COM Strings
* [Why is there a `BSTR` cache anyway?](https://devblogs.microsoft.com/oldnewthing/20150107-00/?p=43203)
* [Raymond’s complete guide to `HSTRING` semantics](https://devblogs.microsoft.com/oldnewthing/20160615-00/?p=93675)
* [What is the correct way of using the string buffer returned by the `WindowsPreallocateStringBuffer` function?](https://devblogs.microsoft.com/oldnewthing/20170913-00/?p=97015)

### COM Variants
* [What’s the difference between `VARIANT` and `VARIANTARG`?](https://devblogs.microsoft.com/oldnewthing/20171221-00/?p=97625)
* [Nasty gotcha: `VarCmp` vs `VariantCompare`](https://devblogs.microsoft.com/oldnewthing/20160218-00/?p=93051)
* [Why can’t `VarDateFromStr` parse back a Hungarian date that was generated by `VarBstrFromDate`?](https://devblogs.microsoft.com/oldnewthing/20161219-00/?p=94965)

### `IUnknown`
* [The layout of a COM object](https://devblogs.microsoft.com/oldnewthing/20040205-00/?p=40733)
* [Under what conditions will the `IUnknown::AddRef` method return 0?](https://devblogs.microsoft.com/oldnewthing/20150312-00/?p=44483)
* [The ways people mess up `IUnknown::QueryInterface`](https://devblogs.microsoft.com/oldnewthing/20040326-00/?p=40033)
* [The ways people mess up `IUnknown::QueryInterface`, episode 2](https://devblogs.microsoft.com/oldnewthing/20090925-00/?p=16583)
* [The ways people mess up `IUnknown::QueryInterface`, episode 3](https://devblogs.microsoft.com/oldnewthing/20091007-00/?p=16463)
* [The ways people mess up `IUnknown::QueryInterface`, episode 4](https://devblogs.microsoft.com/oldnewthing/20110811-00/?p=9923)
* [COM object destructors are very sensitive functions](https://devblogs.microsoft.com/oldnewthing/20050927-13/?p=34023)
* [Avoiding double-destruction when an object is released](https://devblogs.microsoft.com/oldnewthing/20050928-10/?p=34013)
* [I’d like an `IUnknown`, I know you have many, I’ll take any of them](https://devblogs.microsoft.com/oldnewthing/20210101-00/?p=104639)
* [A very brief introduction to patterns for implementing a COM object that hands out references to itself](https://devblogs.microsoft.com/oldnewthing/20211025-00/?p=105828)
* [Giving a single object multiple COM identities, part 1](https://devblogs.microsoft.com/oldnewthing/20211026-00/?p=105834)
* [Giving a single object multiple COM identities, part 2](https://devblogs.microsoft.com/oldnewthing/20211027-00/?p=105838)
* [Giving a single object multiple COM identities, part 3](https://devblogs.microsoft.com/oldnewthing/20211028-00/?p=105852)
* [Giving a single object multiple COM identities, part 4](https://devblogs.microsoft.com/oldnewthing/20211029-00/?p=105859)
* [Reducing chattiness by querying for multiple interfaces at once, part 1](https://devblogs.microsoft.com/oldnewthing/20220315-00/?p=106350)
* [Reducing chattiness by querying for multiple interfaces at once, part 2](https://devblogs.microsoft.com/oldnewthing/20220316-00/?p=106353)


### `IMoniker`
* [Pidls and monikers do roughly the same thing, just backwards](https://devblogs.microsoft.com/oldnewthing/20060712-17/?p=30543)

### `ICallback`
* [A very brief introduction to patterns for implementing a COM object that hands out references to itself](https://devblogs.microsoft.com/oldnewthing/20211025-00/?p=105828)

### `IContextMenu`
* [Why an object cannot be its own enumerator](https://devblogs.microsoft.com/oldnewthing/20040322-00/?p=40143)
* [How to host an `IContextMenu`, part 1 - Initial foray](https://devblogs.microsoft.com/oldnewthing/20040920-00/?p=37823)
* [How to host an `IContextMenu`, part 2 - Displaying the context menu](https://devblogs.microsoft.com/oldnewthing/20040922-00/?p=37793)
* [How to host an `IContextMenu`, part 3 - Invocation location](https://devblogs.microsoft.com/oldnewthing/20040923-00/?p=37773)
* [How to host an `IContextMenu`, part 4 - Key context](https://devblogs.microsoft.com/oldnewthing/20040924-00/?p=37753)
* [How to host an `IContextMenu`, part 5 - Handling menu messages](https://devblogs.microsoft.com/oldnewthing/20040927-00/?p=37733)
* [How to host an `IContextMenu`, part 6 - Displaying menu help](https://devblogs.microsoft.com/oldnewthing/20040928-00/?p=37723)
* [How to host an `IContextMenu`, part 7 - Invoking the default verb](https://devblogs.microsoft.com/oldnewthing/20040930-00/?p=37693)
* [How to host an `IContextMenu`, part 8 - Optimizing for the default command](https://devblogs.microsoft.com/oldnewthing/20041001-00/?p=37683)
* [How to host an `IContextMenu`, part 9 - Adding custom commands](https://devblogs.microsoft.com/oldnewthing/20041004-00/?p=37673)
* [How to host an `IContextMenu`, part 10 - Composite extensions - groundwork](https://devblogs.microsoft.com/oldnewthing/20041006-00/?p=37643)
* [How to host an `IContextMenu`, part 11 - Composite extensions - composition](https://devblogs.microsoft.com/oldnewthing/20041007-00/?p=37633)
* [Simplifying context menu extensions with `IExecuteCommand`](https://devblogs.microsoft.com/oldnewthing/20100312-01/?p=14623)
* [How do I launch a file as if it were a text file, even though its extension is not `.txt`?](https://devblogs.microsoft.com/oldnewthing/20130213-00/?p=5253)
* [Do not access the disk in your `IContextMenu` handler, no really, don't do it](https://devblogs.microsoft.com/oldnewthing/20111003-00/?p=9493)
* [Sure, we do that: Context menu edition](https://devblogs.microsoft.com/oldnewthing/20120516-00/?p=7613)
* [Psychic debugging: Why your `IContextMenu::InvokeCommand` doesn't get called even though you returned success from `IContextMenu::QueryContextMenu`](https://devblogs.microsoft.com/oldnewthing/20130201-00/?p=5383)
* [Don’t forget to implement canonical names for verbs in your shell context menu extension](https://devblogs.microsoft.com/oldnewthing/20170302-00/?p=95635)

### `IFileDialog`
* [The `SetClientGuid` method of the common file and folder dialogs lets you give names to those dialogs, too](https://devblogs.microsoft.com/oldnewthing/20200527-00/?p=103801) (multiple contexts for open/save dialogs)
* [How can I get my `FileSavePicker` to open in the same folder that was picked by the `FileOpenPicker` or `FolderPicker`?](https://devblogs.microsoft.com/oldnewthing/20220525-00/?p=106685) (win32/COM equivalent mentioned at the end of the post)
* [Why does IFileDialog still show non-filesystem folders when I pass `FOS_FORCE­FILE­SYSTEM`?](https://devblogs.microsoft.com/oldnewthing/20231011-00/?p=108884)


### `IMultiLanguage`
* [Converting between `LCID`s and RFC 1766 language codes](https://devblogs.microsoft.com/oldnewthing/20060105-00/?p=32753)
* [Feel free to stop using `IMultiLanguage2::DetectInputCodepage`](https://devblogs.microsoft.com/oldnewthing/20221003-00/?p=107241)


### `INamespaceWalk`
* [How can I control which parts of the shell namespace the `INamespaceWalk::Walk` operation will walk into?](https://devblogs.microsoft.com/oldnewthing/20171108-00/?p=97365)
* [How can I cancel the `INamespace­Walk::Walk` operation?](https://devblogs.microsoft.com/oldnewthing/20171109-00/?p=97375)
* [Cancelling the `INamespace­Walk::Walk` operation a little faster](https://devblogs.microsoft.com/oldnewthing/20171110-00/?p=97385)

### `IStream`
* [The subtleties of `Create­Stream­On­HGlobal`, part 1: Introduction and basic usage](https://devblogs.microsoft.com/oldnewthing/20210928-00/?p=105737)
* [The subtleties of `Create­Stream­On­HGlobal`, part 2: Suppressing the deletion of an unknown `HGLOBAL`](https://devblogs.microsoft.com/oldnewthing/20210929-00/?p=105742)
* [The subtleties of `Create­Stream­On­HGlobal`, part 3: Suppressing the deletion of a shared `HGLOBAL`](https://devblogs.microsoft.com/oldnewthing/20210930-00/?p=105745)
* [The subtleties of `Create­Stream­On­HGlobal`, part 4: Non-movable memory](https://devblogs.microsoft.com/oldnewthing/20211001-00/?p=105748)
* [A practical use for `GetHGlobal­FromStream` when sharing was never your intention](https://devblogs.microsoft.com/oldnewthing/20211115-00/?p=105922)

### `IVirtual­Desktop­Manager`
* [Virtual desktops are an end-user window management feature, not a programmatic one](https://devblogs.microsoft.com/oldnewthing/20201123-00/?p=104476)

### Clipboard
* [How ownership of the Windows clipboard is tracked in Win32](https://devblogs.microsoft.com/oldnewthing/20210526-00/?p=105252)
* [What happens when applications try to copy text by sending `Ctrl+C`](https://devblogs.microsoft.com/oldnewthing/20110623-00/?p=10353)
* [How do I make it so that users can copy static text on a dialog box to the clipboard easily?](https://devblogs.microsoft.com/oldnewthing/20120301-00/?p=8193)
* [What is the proper handling of `WM_RENDERFORMAT` and `WM_RENDERALLFORMATS`?](https://devblogs.microsoft.com/oldnewthing/20121224-00/?p=5763)
* [Copying a file to the clipboard so you can paste it into Explorer or an email message or whatever](https://devblogs.microsoft.com/oldnewthing/20130520-00/?p=4313)
* [Printing the contents of the clipboard as text to `stdout`](https://devblogs.microsoft.com/oldnewthing/20131007-00/?p=3023)
* [Improving the performance of `CF_HDROP` by providing file attribute information](https://devblogs.microsoft.com/oldnewthing/20140609-00/?p=783)
* [What’s up with the `CF_SYLK` and `CF_DIF` clipboard formats?](https://devblogs.microsoft.com/oldnewthing/20200226-00/?p=103489)
* [How can I wait more than 30 seconds for a delay-rendered clipboard format to become rendered?](https://devblogs.microsoft.com/oldnewthing/20220609-00/?p=106731)

### Drag and Drop
* [What a drag: Dragging text](https://devblogs.microsoft.com/oldnewthing/20080311-00/?p=23153)
* [What a drag: Dragging a Uniform Resource Locator (URL)](https://devblogs.microsoft.com/oldnewthing/?p=23133)
* [What a drag: Dragging a Uniform Resource Locator (URL) and text](https://devblogs.microsoft.com/oldnewthing/20080313-00/?p=23123)
* [What a drag: Dragging a virtual file (`HGLOBAL` edition)](https://devblogs.microsoft.com/oldnewthing/?p=23083)
* [What a drag: Dragging a virtual file (`IStream` edition)](https://devblogs.microsoft.com/oldnewthing/20080319-00/?p=23073)
* [What a drag: Dragging a virtual file (`IStorage` edition)](https://devblogs.microsoft.com/oldnewthing/20080320-00/?p=23063)
* [You can drag multiple virtual objects, you know](https://devblogs.microsoft.com/oldnewthing/20080331-00/?p=22933)
* [Reading a contract from the other side: Simulating a drop](https://devblogs.microsoft.com/oldnewthing/20080724-00/?p=21483)
* [Simulating a drop, part two](https://devblogs.microsoft.com/oldnewthing/20080725-00/?p=21473)
* [What happens if I drag the mouse by exactly the amount specified by `SM_CXDRAG`?](https://devblogs.microsoft.com/oldnewthing/20100304-00/?p=14733)
* [How do I accept files to be opened via `IDropTarget` instead of on the command line?](https://devblogs.microsoft.com/oldnewthing/20100503-00/?p=14183)
* [How do I accept files to be opened via `IDropTarget` instead of on the command line? - bonus content](https://devblogs.microsoft.com/oldnewthing/20100528-01/?p=13883)
* [Using Explorer’s fancy drag/drop effects in your own programs](https://devblogs.microsoft.com/oldnewthing/20210512-00/?p=105208)
* [Drag/drop effects: The little drop information box](https://devblogs.microsoft.com/oldnewthing/20210513-00/?p=105212)
* [Why isn’t my shell namespace extension getting every single `DragOver` mouse message?](https://devblogs.microsoft.com/oldnewthing/20210514-00/?p=105214)
* [Why doesn’t my program get fancy drag/drop effects in high contrast mode with `CLSID_Drag­Drop­Helper`?](https://devblogs.microsoft.com/oldnewthing/20240207-00/?p=109372)

### Enumeration
* [Using fibers to simplify enumerators, part 1: When life is easier for the enumerator](https://devblogs.microsoft.com/oldnewthing/20041229-00/?p=36853)
* [Using fibers to simplify enumerators, part 2: When life is easier for the caller](https://devblogs.microsoft.com/oldnewthing/20041230-00/?p=36843)
* [Using fibers to simplify enumerators, part 3: Having it both ways](https://devblogs.microsoft.com/oldnewthing/20041231-00/?p=36833)
* [Using fibers to simplify enumerators, part 4: Filtering](https://devblogs.microsoft.com/oldnewthing/20050103-00/?p=36823)
* [Using fibers to simplify enumerators, part 5: Composition](https://devblogs.microsoft.com/oldnewthing/20050104-00/?p=36813)

### Shell
* [When does `SHLoadInProc` unload a DLL?](https://devblogs.microsoft.com/oldnewthing/20040628-00/?p=38663)
* [What does `SHGFI_USEFILEATTRIBUTES` mean?](https://devblogs.microsoft.com/oldnewthing/20040601-00/?p=39073)
* [What's the difference between `SHGetMalloc`, `SHAlloc`, `CoGetMalloc`, and `CoTaskMemAlloc`](https://devblogs.microsoft.com/oldnewthing/20040705-00/?p=38573)
* [Querying information from an Explorer window](https://devblogs.microsoft.com/oldnewthing/20040720-00/?p=38393)
* [Execute a file as if it were a program, even though its extension is not `EXE`](https://devblogs.microsoft.com/oldnewthing/20140210-00/?p=1823)
* [How do I launch a file as if it were a text file, even though its extension is not `.txt`?](https://devblogs.microsoft.com/oldnewthing/20130213-00/?p=5253)
* [What does the `SEE_MASK_UNICODE` flag in `ShellExecuteEx` actually do?](https://devblogs.microsoft.com/oldnewthing/20140227-00/?p=1643)
* [Simple things you can do with the `ShellExecuteEx` function](https://devblogs.microsoft.com/oldnewthing/20041126-00/?p=37193)
* [What were `ShellExecute` hooks designed for?](https://devblogs.microsoft.com/oldnewthing/20080910-00/?p=20933)
* [Why does `ShellExecute` return `SE_ERR_ACCESSDENIED` for nearly everything?](https://devblogs.microsoft.com/oldnewthing/20121018-00/?p=6303)
* [How do I `ShellExecute` a file, but with a specific program instead of the default program?](https://devblogs.microsoft.com/oldnewthing/20171220-00/?p=97615)
* [What is the difference between `CSIDL_DESKTOP` and `CSIDL_DESKTOPDIRECTORY`?](https://devblogs.microsoft.com/oldnewthing/20090730-00/?p=17293)
* [`SHCIDS_CANONICALONLY` is the moral equivalent in the shell namespace of the Unicode ordinal comparison](https://devblogs.microsoft.com/oldnewthing/20090807-00/?p=17193)
* [Don't forget to double-null-terminate those strings you pass to `SHFileOperation`](https://devblogs.microsoft.com/oldnewthing/20100218-00/?p=14893)
* [Why does `SHFileOperation` have internal error codes for DVD?](https://devblogs.microsoft.com/oldnewthing/20100322-00/?p=14533)
* [Why do non-folders in my shell namespace extension show up in the folder tree view?](https://devblogs.microsoft.com/oldnewthing/20100402-00/?p=14413)
* [`SHAutoComplete` giveth, and `SHAutoComplete` taketh away](https://devblogs.microsoft.com/oldnewthing/20100521-00/?p=13963)
* [What is the `lpClass` member of `SHELLEXECUTEINFO` used for?](https://devblogs.microsoft.com/oldnewthing/20100701-00/?p=13543)
* [Some known folders cannot be moved, but others can, and you'll just have to accept that](https://devblogs.microsoft.com/oldnewthing/20100806-00/?p=13213)
* [One possible reason why `ShellExecute` returns `SE_ERR_ACCESSDENIED` and `ShellExecuteEx` returns `ERROR_ACCESS_DENIED`](https://devblogs.microsoft.com/oldnewthing/20101118-00/?p=12253)
* [Why does `SHGetSpecialFolderPath` take such a long time before returning a network error?](https://devblogs.microsoft.com/oldnewthing/20110105-00/?p=11823)
* [How do you obtain the icon for a shortcut without the shortcut overlay?](https://devblogs.microsoft.com/oldnewthing/20110127-00/?p=11653) (`SHGetFileInfo()`)
* [How can I get information about the items in the Recycle Bin?](https://devblogs.microsoft.com/oldnewthing/20110830-00/?p=9773)
* [Modernizing our simple program that retrieves information about the items in the Recycle Bin](https://devblogs.microsoft.com/oldnewthing/20110831-00/?p=9763)
* [Invoking commands on items in the Recycle Bin](https://devblogs.microsoft.com/oldnewthing/20110901-00/?p=9753)
* [How do I perform shell file operations while avoiding shell copy hooks?](https://devblogs.microsoft.com/oldnewthing/20120330-00/?p=7963)
* [Command line tool to manage Windows 7 Libraries, with source code](https://devblogs.microsoft.com/oldnewthing/20120828-01/?p=6743) (`IShellLibrary`)
* [`IShellFolder::BindToObject` is a high-traffic method; don't do any heavy lifting](https://devblogs.microsoft.com/oldnewthing/20120914-00/?p=6603)
* [Obtaining the parsing name (and pidl) for a random shell object](https://devblogs.microsoft.com/oldnewthing/20130204-00/?p=5363)
* [Creating a simple pidl: For the times you care enough to send the very fake](https://devblogs.microsoft.com/oldnewthing/20130503-00/?p=4463)
* [Creating a simple shell item, just as fake as a simple pidl](https://devblogs.microsoft.com/oldnewthing/20140519-00/?p=963)
* [Displaying a property sheet for multiple files](https://devblogs.microsoft.com/oldnewthing/20130617-00/?p=4073)
* [How do I get a high resolution icon for a file?](https://devblogs.microsoft.com/oldnewthing/20140120-00/?p=2043)
* [How do I extract an icon at a nonstandard size if `IExtractIcon::Extract` tells me to go jump in a lake?](https://devblogs.microsoft.com/oldnewthing/20140501-00?p=1103)
* [How do I read the "Double-click to open an item (single-click to select)" setting in Folder Options?](https://devblogs.microsoft.com/oldnewthing/20140825-00/?p=153)
* [The wonderful world of shell bind context strings](https://devblogs.microsoft.com/oldnewthing/20150122-00/?p=44853)
* [Helper functions to make shell bind contexts slightly more manageable](https://devblogs.microsoft.com/oldnewthing/20150123-00/?p=44843)
* [Customizing item enumeration with `IShellItem`](https://devblogs.microsoft.com/oldnewthing/20150126-00/?p=44833)
* [Customizing item enumeration with `IShellItem`, the old-fashioned way](https://devblogs.microsoft.com/oldnewthing/20150202-00/?p=44773)
* [How do I create an `IShellItemArray` from a bunch of file paths?](https://devblogs.microsoft.com/oldnewthing/20140314-00/?p=1503)
* [How do I invoke a verb on an `IShellItemArray`?](https://devblogs.microsoft.com/oldnewthing/20120920-00/?p=6553)
* [How does a shell namespace extension provide icons for virtual items that track the standard icons set by the user's file associations?](https://devblogs.microsoft.com/oldnewthing/20151009-00/?p=91401)
* [How do I get the user-customed name of My Computer or Recycle Bin?](https://devblogs.microsoft.com/oldnewthing/20151012-00/?p=91381)
* [How do I get the user-customized name of a mapped network drive?](https://devblogs.microsoft.com/oldnewthing/20151019-00/?p=91331)
* [Enumerating all the programs that can open a particular file extension](https://devblogs.microsoft.com/oldnewthing/20151130-00/?p=92191)
* [Enumerating all the programs that can launch a particular protocol](https://devblogs.microsoft.com/oldnewthing/20151207-00/?p=92341)
* [How do I register a command on the desktop background context menu? (And how do I remove one I don’t like?)](https://devblogs.microsoft.com/oldnewthing/20151208-00/?p=92342)
* [How can I get the canonical name for a known folder?](https://devblogs.microsoft.com/oldnewthing/20160208-00/?p=93001)
* [Peeking inside an `IShellItem` to see what it’s made of](https://devblogs.microsoft.com/oldnewthing/20160620-00/?p=93705)
* [Why does `SHGetKnownFolderPath` return `E_FAIL` for a known folder?](https://devblogs.microsoft.com/oldnewthing/20110209-00/?p=11543)
* [Why does `SHGetKnownFolderPath` fail when impersonating?](https://devblogs.microsoft.com/oldnewthing/20160601-00/?p=93555)
* [Why can’t I use `SHSetKnownFolderPath` to change the location of `FOLDERID_LocalAppData`?](https://devblogs.microsoft.com/oldnewthing/20200115-00/?p=103329)
* [How do I programmatically add a folder to my Documents library?](https://devblogs.microsoft.com/oldnewthing/20161107-00/?p=94655)
* [Why doesn’t `SHGetFileInfo` give me customized folder icons?](https://devblogs.microsoft.com/oldnewthing/20170501-00/?p=96075)
* [How can I detect that a shell item refers to a virtual folder, or to a file system inside a file?](https://devblogs.microsoft.com/oldnewthing/20171101-00/?p=97325)
* [Why is there a limit of 15 shell icon overlays?](https://devblogs.microsoft.com/oldnewthing/20190313-00/?p=101094)
* [The case of the `SHGet­Folder­Path(CSIDL_COMMON_DOCUMENTS)` that returned `ERROR_PATH_NOT_FOUND`](https://devblogs.microsoft.com/oldnewthing/20200520-00/?p=103775)
* [Why is the `HSHELL_WINDOWDESTROYED` notification raised when a window is hidden, even if it hasn’t been destroyed?](https://devblogs.microsoft.com/oldnewthing/20201228-00/?p=104610)
* [Why am I receiving `HCNE_UPDATEDIR` notifications that my code never generates?](https://devblogs.microsoft.com/oldnewthing/20210112-00/?p=104707)
* [Why am I receiving `SHCNE_UPDATE­DIR` notifications that my code never generates?](https://devblogs.microsoft.com/oldnewthing/20220923-00/?p=107209)
* [How can I get the original target of a shortcut without applying any 32-bit adjustments?](https://devblogs.microsoft.com/oldnewthing/20230208-00/?p=107807)
* [How does Explorer calculate the “Date” of a file?](https://devblogs.microsoft.com/oldnewthing/20230921-00/?p=108808)

### Uncategorized COM Stuff
* [The macros for declaring and implementing COM interfaces](https://devblogs.microsoft.com/oldnewthing/20041005-00/?p=37653)
* [An introduction to COM connection points](https://devblogs.microsoft.com/oldnewthing/20130611-00/?p=4113)
* [Dispatch interfaces as connection point interfaces](https://devblogs.microsoft.com/oldnewthing/20130612-00/?p=4103)
* [Adjustor thunks](https://devblogs.microsoft.com/oldnewthing/20040206-00/?p=40723)
* [What is the underlying object behind a COM interface pointer?](https://devblogs.microsoft.com/oldnewthing/20070424-00/?p=27143)
* [How to turn off the exception handler that COM "helpfully" wraps around your server](https://devblogs.microsoft.com/oldnewthing/20110120-00/?p=11713)
* [Shortcuts are serializable objects, which means that they can be stored in places other than just a file](https://devblogs.microsoft.com/oldnewthing/20110224-00/?p=11403)
* [Why does `IFileOperation` skip junctions even though I passed `FOFX_NOSKIPJUNCTIONS`?](https://devblogs.microsoft.com/oldnewthing/20110818-00/?p=9873)
* [Nasty gotcha: `STGM_READ | STGM_WRITE` does not grant read/write access](https://devblogs.microsoft.com/oldnewthing/20130719-00/?p=3763)
* [How can I get the list of programs the same way that Programs and Features gets it?](https://devblogs.microsoft.com/oldnewthing/20131230-00/?p=2233)
* [How do I obtain the computer manufacturer's name via C++?](https://devblogs.microsoft.com/oldnewthing/20140106-00/?p=2163) (`IWbemClassObject`)
* [The stream pointer position in `IDataObject::GetData` and `IDataObject::GetDataHere` is significant](https://devblogs.microsoft.com/oldnewthing/20140918-00/?p=44033)
* [The sad implementation history of COM component categories and why it means you have to click twice to see your newly-installed taskbar toolbar](https://devblogs.microsoft.com/oldnewthing/20171121-00/?p=97435)
* [How do I request that my out-of-process COM server run unelevated?](https://devblogs.microsoft.com/oldnewthing/20180905-00/?p=99655)
* [How can a desktop app use a Windows Runtime object that infers UI context from its thread? The `IInitializeWithWindow` pattern](https://devblogs.microsoft.com/oldnewthing/20190412-00/?p=102413) (`IInitialize­With­Window`)
* [How do I protect myself against a COM call that can hang? I’m already running the server out-of-process.](https://devblogs.microsoft.com/oldnewthing/20210122-00/?p=104750)
* [What can I do about timer build-up when waiting for COM outbound calls to complete?](https://devblogs.microsoft.com/oldnewthing/20211008-50/?p=105780)
* [Manipulating the positions of desktop icons](https://devblogs.microsoft.com/oldnewthing/20130318-00/?p=4933)
* [A reminder about the correct way of accessing and manipulating the position of icons on the desktop](https://devblogs.microsoft.com/oldnewthing/20211122-00/?p=105948)
* [The oracle always tells the truth, even when it is wrong: COM method calls with a user-defined type as a return value](https://devblogs.microsoft.com/oldnewthing/20220113-00/?p=106152) (on problems of COM interfaces called from C code)
* [Notes on COM aggregation: Obtaining a pointer to your aggregated partner without introducing a reference cycle](https://devblogs.microsoft.com/oldnewthing/20220210-00/?p=106243)
* [Notes on COM aggregation: How do you implement tear-offs in an aggregated object?](https://devblogs.microsoft.com/oldnewthing/20220211-00/?p=106246)
* [The theory behind the `IHttpFilter` interface](https://devblogs.microsoft.com/oldnewthing/20231117-00/?p=109028)


## Memory

* [Stupid memory-mapping tricks](https://devblogs.microsoft.com/oldnewthing/20031007-00/?p=42263)
* [Creating a shared memory block that can grow in size](https://devblogs.microsoft.com/oldnewthing/20150130-00/?p=44793)
* [Why do I have to pass a valid page protection value to `VirtualAlloc` even if it ignores it?](https://devblogs.microsoft.com/oldnewthing/20171227-00/?p=97656)
* [How can I include/exclude specific memory blocks in user-mode crash dumps?](https://devblogs.microsoft.com/oldnewthing/20181011-00/?p=99945)
* [`IsBadXxxPtr` should really be called CrashProgramRandomly](https://devblogs.microsoft.com/oldnewthing/20060927-07/?p=29563) (`IsBadWritePtr()` et al.)
* [A closer look at the stack guard page](https://devblogs.microsoft.com/oldnewthing/20220203-00/?p=106215)
* [The case of the stack overflow exception when the stack is nowhere near overflowing](https://devblogs.microsoft.com/oldnewthing/20220204-00/?p=106219)
* [How to allocate address space with a custom alignment or in a custom address region](https://devblogs.microsoft.com/oldnewthing/20231229-00/?p=109204)


## Input and Output

* [Mount points, volumes, and physical drives, oh my!](https://devblogs.microsoft.com/oldnewthing/20201019-00/?p=104380)
* [What's the difference between an asynchronous `PIPE_WAIT` pipe and a `PIPE_NOWAIT` pipe?](https://devblogs.microsoft.com/oldnewthing/20110114-00/?p=11753)
* [Be careful when redirecting both a process's `stdin` and `stdout` to pipes, for you can easily deadlock](https://devblogs.microsoft.com/oldnewthing/20110707-00/?p=10223)
* [Looking at the problem at the wrong level: Closing a process's `stdin`](https://devblogs.microsoft.com/oldnewthing/20110706-00/?p=10243)
* [`ReadDirectoryChangesW` reads directory changes, but what if the directory doesn't change?](https://devblogs.microsoft.com/oldnewthing/20110812-00/?p=9913)
* [How do `FILE_FLAG_SEQUENTIAL_SCAN` and `FILE_FLAG_RANDOM_ACCESS` affect how the operating system treats my file?](https://devblogs.microsoft.com/oldnewthing/20120120-00/?p=8493)
* [I used `FILE_FLAG_SEQUENTIAL_SCAN` but it didn’t seem to speed up my sequential scanning](https://devblogs.microsoft.com/oldnewthing/20221130-00/?p=107505)
* [You can use an `OVERLAPPED` structure with synchronous I/O, too](https://devblogs.microsoft.com/oldnewthing/20120405-00/?p=7923)
* [We're currently using `FILE_FLAG_NO_BUFFERING` and `FILE_FLAG_WRITE_THROUGH`, but we would like our `WriteFile` to go even faster](https://devblogs.microsoft.com/oldnewthing/20140306-00/?p=1583)
* [On using `ILE_FLAG_WRITE_THROUGH` and `FILE_FLAG_NO_BUFFERING` for memory-mapped files](https://devblogs.microsoft.com/oldnewthing/20200819-00/?p=104093)
* [On the interaction between the `FILE_FLAG_NO_BUFFERING` and `FILE_FLAG_WRITE_THROUGH` flags](https://devblogs.microsoft.com/oldnewthing/20210729-00/?p=105494)
* [Why does my synchronous overlapped `ReadFile` return `FALSE` when the end of the file is reached?](https://devblogs.microsoft.com/oldnewthing/20150121-00/?p=44863)
* [Why does `SetFileValidData` fail even though I enabled the `SE_MANAGE_VOLUME_NAME` privilege?](https://devblogs.microsoft.com/oldnewthing/20160603-00/?p=93565)
* [Is `GENERIC_ALL` equivalent to `GENERIC_READ | GENERIC_WRITE | GENERIC_EXECUTE`?](https://devblogs.microsoft.com/oldnewthing/20170310-00/?p=95705)
* [`CancelIoEx` can cancel I/O on console input, which is kind of nice](https://devblogs.microsoft.com/oldnewthing/20150323-00/?p=44413)
* [`CancelIoEx` can cancel synchronous I/O, which is kind of nice](https://devblogs.microsoft.com/oldnewthing/20170928-00/?p=97105)
* [Why does `IsPathRelative` return `FALSE` for paths that are drive-relative?](https://devblogs.microsoft.com/oldnewthing/20180222-00/?p=98075)
* [The security check happens at the acquisition of the handle](https://devblogs.microsoft.com/oldnewthing/20200320-00/?p=103579)
* [Taking a shortcut: You can query properties from a volume, and it will forward to the physical drive](https://devblogs.microsoft.com/oldnewthing/20201022-00/?p=104391)
* [https://devblogs.microsoft.com/oldnewthing/20201023-00/?p=104395](https://devblogs.microsoft.com/oldnewthing/20201023-00/?p=104395)
* [How do I disassociate a thread from an I/O completion port?](https://devblogs.microsoft.com/oldnewthing/20210120-00/?p=104740)
* [Is it okay to call `Map­View­Of­File` on the same mapping handle simultaneously from different threads?](https://devblogs.microsoft.com/oldnewthing/20210702-00/?p=105392)
* [What are these dire multithreading consequences that the `GetFullPathName` documentation is trying to warn me about?](https://devblogs.microsoft.com/oldnewthing/20210816-00/?p=105562)
* [How can I force a `WriteFile` or `ReadFile` to complete synchronously or hang, in order to test something?](https://devblogs.microsoft.com/oldnewthing/20220425-00/?p=106526)
* [How can I perform a `CopyFile`, but also flush the file buffers before the destination handle is closed?](https://devblogs.microsoft.com/oldnewthing/20221007-00/?p=107261)

### Asynchronous Input and Output
* [Developing the method for taking advantage of the fact that the `OVERLAPPED` associated with asynchronous I/O is passed by address](https://devblogs.microsoft.com/oldnewthing/20101220-01/?p=11963)
* [Ready... cancel... wait for it! (part 1)](https://devblogs.microsoft.com/oldnewthing/20110202-00/?p=11613)
* [Ready... cancel... wait for it! (part 2)](https://devblogs.microsoft.com/oldnewthing/20110203-00/?p=11603)
* [Ready... cancel... wait for it! (part 3)](https://devblogs.microsoft.com/oldnewthing/20110204-00/?p=11583)
* [If you're waiting for I/O to complete, it helps if you actually have an I/O to begin with](https://devblogs.microsoft.com/oldnewthing/20110303-00/?p=11313)
* [Why does my asynchronous I/O complete synchronously?](https://devblogs.microsoft.com/oldnewthing/20110923-00/?p=9563)
* [If an asynchronous I/O completes synchronously, is the `hEvent` in the `OVERLAPPED` structure signaled anyway?](https://devblogs.microsoft.com/oldnewthing/20140206-00/?p=1853)
* [You can use an `OVERLAPPED` structure with synchronous I/O, too](https://devblogs.microsoft.com/oldnewthing/20120405-00/?p=7923)
* [Why does my synchronous overlapped `ReadFile` return `FALSE` when the end of the file is reached?](https://devblogs.microsoft.com/oldnewthing/20150121-00/?p=44863)
* [If I issue a second overlapped I/O operation without waiting for the first one to complete, are they still guaranteed to complete in order?](https://devblogs.microsoft.com/oldnewthing/20160205-00/?p=92981)
* [Why are my file write operations synchronous, even though I opened the file as `FILE_FLAG_OVERLAPPED`?](https://devblogs.microsoft.com/oldnewthing/20180725-00/?p=99335)
* [File-extending writes are not always synchronous, which is entirely within the contract](https://devblogs.microsoft.com/oldnewthing/20181019-00/?p=100015)
* [Why you might need additional control over the secret event hiding inside the file object](https://devblogs.microsoft.com/oldnewthing/20200221-00/?p=103466)
* [Why doesn’t my asynchronous read operation complete when I close the handle?](https://devblogs.microsoft.com/oldnewthing/20210730-00/?p=105501)
* [The mental model for `StartThreadpoolIo`](https://devblogs.microsoft.com/oldnewthing/20211117-00/?p=105933)
* [How can I force a `WriteFile` or `ReadFile` to complete synchronously or hang, in order to test something?](https://devblogs.microsoft.com/oldnewthing/20220425-00/?p=106526)
* [If I issue multiple overlapped I/O requests against the same region of a file, will they execute in the order I issued them?](https://devblogs.microsoft.com/oldnewthing/20221111-00/?p=107385)
* [What are the potentially-erroneous results if you don’t pass `NULL` as the `lpNumberOfBytesRead` when issuing overlapped I/O?](https://devblogs.microsoft.com/oldnewthing/20230215-00/?p=107832)

### Files and Directories
* [The Definitive Guide on Win32 to NT Path Conversion](http://googleprojectzero.blogspot.cz/2016/02/the-definitive-guide-on-win32-to-nt.html)
* [How can I tell that a directory is really a recycle bin?](https://devblogs.microsoft.com/oldnewthing/20080918-00/?p=20843)
* [How can I tell that a directory is weird and should be excluded from the user interface?](https://devblogs.microsoft.com/oldnewthing/20080919-00/?p=20833)
* [How do I get information about the target of a symbolic link?](https://devblogs.microsoft.com/oldnewthing/20100212-00/?p=14963)
* [How do I access a file without updating its last-access time?](https://devblogs.microsoft.com/oldnewthing/20111010-00/?p=9433)
* [How do I show the contents of a directory while respecting the user's preferences for hidden and super-hidden files as well as the user's language preferences?](https://devblogs.microsoft.com/oldnewthing/20140317-00/?p=1493)
* [You can use a file as a synchronization object, too](https://devblogs.microsoft.com/oldnewthing/20140905-00/?p=63)
* [How can I append to a file and know where it got written, even if the file is being updated by multiple processes?](https://devblogs.microsoft.com/oldnewthing/20151127-00/?p=92211)
* [The `FILE_FLAG_DELETE_ON_CLOSE` flag applies to the handle, also known as the file object, which is not the same as the file](https://devblogs.microsoft.com/oldnewthing/20160108-00/?p=92821)
* [How long do I have to keep the `SECURITY_ATTRIBUTES` and `SECURITY_DESCRIPTOR` structures valid after using them to create a file?](https://devblogs.microsoft.com/oldnewthing/20160520-00/?p=93497)
* [How do I create a directory where people can create subdirectories but cannot mess with those created by other users?](https://devblogs.microsoft.com/oldnewthing/20160524-00/?p=93515)
* [How can I tell whether a file is on a removable drive, a fixed drive, or a remote drive?](https://devblogs.microsoft.com/oldnewthing/20160602-00/?p=93556)
* [How can I tell whether a file is on an SSD?](https://devblogs.microsoft.com/oldnewthing/20201023-00/?p=104395)
* [Why does a non-recursive `Read­Directory­ChangesW` still report files created inside subdirectories?](https://devblogs.microsoft.com/oldnewthing/20180712-00/?p=99225)
* [The early history of Windows file attributes, and why there is a gap between System and Directory](https://devblogs.microsoft.com/oldnewthing/20180830-00/?p=99615)
* [Even if you open a file with GUID, you can still get its name, or at least one of its names](https://devblogs.microsoft.com/oldnewthing/20190410-00/?p=102408) (`GetFinalPathNameByHandle()`)
* [How do I get from a file path to the volume that holds it?](https://devblogs.microsoft.com/oldnewthing/20201020-00/?p=104385)
* [How do I get from a volume to the physical disk that holds it?](https://devblogs.microsoft.com/oldnewthing/20201021-00/?p=104387)
* [Renaming a file is a multi-step process, only one of which is changing the name of the file
](https://devblogs.microsoft.com/oldnewthing/20211022-00/?p=105822)
* [How can I recognize file systems that don’t support 64-bit unique file identifiers?](https://devblogs.microsoft.com/oldnewthing/20220127-00/?p=106199)
* [How can I recognize whether two handles refer to the same underlying file?](https://devblogs.microsoft.com/oldnewthing/20220128-00/?p=106201)

### ACL
* [The `MoveSecurityAttributes` policy affects only how Explorer recalculates ACLs when a file is moved; everybody else is on their own](https://devblogs.microsoft.com/oldnewthing/20151014-00/?p=91361)
* [How to create a folder that inherits its parent’s ACL, and then overrides part of it](https://devblogs.microsoft.com/oldnewthing/20170223-00/?p=95545)


## Security Permissions, Attributes and Identifiers

* [The security check happens at the acquisition of the handle](https://devblogs.microsoft.com/oldnewthing/20200320-00/?p=103579)
* [What is the default security descriptor?](https://devblogs.microsoft.com/oldnewthing/20040312-00/?p=40273)
* [How do I convert a SID between binary and string forms?](https://devblogs.microsoft.com/oldnewthing/20150501-00/?p=40253)
* [What are these SIDs of the form `S-1-15-2-xxx`?](https://devblogs.microsoft.com/oldnewthing/20220502-00/?p=106550)
* [What are these SIDs of the form `S-1-15-3-xxx`?](https://devblogs.microsoft.com/oldnewthing/20220503-00/?p=106557)
* [An easy way to determine whether you have a particular file permission](https://devblogs.microsoft.com/oldnewthing/20040604-00/?p=39023)
* [What are the access rights and privileges that control changing ownership of an object?](https://devblogs.microsoft.com/oldnewthing/20050818-09/?p=34533)
* [How do the names in the file security dialog map to access control masks?](https://devblogs.microsoft.com/oldnewthing/20070726-00/?p=25833)
* [If you ask for `STANDARD_RIGHTS_REQUIRED`, you may as well ask for the moon](https://devblogs.microsoft.com/oldnewthing/20080227-00/?p=23303)
* [A user's SID can change, so make sure to check the SID history](https://devblogs.microsoft.com/oldnewthing/20141128-00/?p=43513)
* [Detecting whether a SID is well-known SID](https://devblogs.microsoft.com/oldnewthing/20141212-00/?p=43413)
* [SIDs are really just another a fancy way of creating unique IDs in a decentralized way](https://devblogs.microsoft.com/oldnewthing/20230613-00/?p=108335)
* [What's the point of giving my unnamed object proper security attributes since unnamed objects aren't accessible outside the process anyway (or are they?)](https://devblogs.microsoft.com/oldnewthing/20150604-00/?p=45451)
* [Is a SID with zero subauthorities a valid SID? It depends whom you ask](https://devblogs.microsoft.com/oldnewthing/?p=45231)
* [What’s the difference between duplicating the handle to a token and duplicating a token?](https://devblogs.microsoft.com/oldnewthing/20160511-00/?p=93446)
* [I called `AdjustTokenPrivileges`, but I was still told that a necessary privilege was not held](https://devblogs.microsoft.com/oldnewthing/20190531-00/?p=102532)
* [I called `AdjustTokenPrivileges`, but I was still told that a necessary privilege was not held, redux](https://devblogs.microsoft.com/oldnewthing/20211126-00/?p=105973)
* [The history of the `EncodePointer` function for obfuscating pointers](https://devblogs.microsoft.com/oldnewthing/20201113-00/?p=104447)
* [Additional helpful pseudo-handles: The process token, the thread token, and the effective token](https://devblogs.microsoft.com/oldnewthing/20210105-00/?p=104667)
* [How can I tell whether my process is running as SYSTEM?](https://devblogs.microsoft.com/oldnewthing/20210106-00/?p=104669)
* [A brief summary of the various versions of the Security Descriptor Definition Language (SDDL)](https://devblogs.microsoft.com/oldnewthing/20220510-00/?p=106640)
* [How do I free the pointers returned by functions like `Get­Token­Information`?](https://devblogs.microsoft.com/oldnewthing/20230517-00/?p=108207)
* [A clarification on the multithreading constraints of the `Encrypt­Message` function](https://devblogs.microsoft.com/oldnewthing/20231109-00/?p=108988)


## Registry

* [Beware of non-null-terminated registry strings](https://devblogs.microsoft.com/oldnewthing/20040824-00/?p=38063)
* [The performance cost of reading a registry key](https://devblogs.microsoft.com/oldnewthing/20060222-11/?p=32193)
* [So how bad is it that I’m calling `RegOpenKey` instead of `RegOpenKeyEx`?](https://devblogs.microsoft.com/oldnewthing/20160120-00/?p=92892)
* [If I simply want to create a registry key but don’t intend to do anything else with it, what security access mask should I ask for?](https://devblogs.microsoft.com/oldnewthing/20161128-00/?p=94815)
* [How can I programmatically inspect and manipulate a registry hive file without mounting it?](https://devblogs.microsoft.com/oldnewthing/20181015-00/?p=99975)
* [Why doesn’t `RegSetKeySecurity` propagate inheritable ACEs, but `SetSecurityInfo` does?](https://devblogs.microsoft.com/oldnewthing/20200102-00/?p=103287)
* [Why does `Reg­Notify­Change­Key­Value` stop notifying once the key is deleted?](https://devblogs.microsoft.com/oldnewthing/20200507-00/?p=103733)
* [How can I emulate the `REG_NOTIFY_THREAD_AGNOSTIC` flag on systems that don’t support it? part 1](https://devblogs.microsoft.com/oldnewthing/20201221-00/?p=104574)
* [How can I emulate the `REG_NOTIFY_THREAD_AGNOSTIC` flag on systems that don’t support it? part 2](https://devblogs.microsoft.com/oldnewthing/20201222-00/?p=104582)
* [How can I emulate the `REG_NOTIFY_THREAD_AGNOSTIC` flag on systems that don’t support it? part 3](https://devblogs.microsoft.com/oldnewthing/20201223-00/?p=104584)
* [How can I emulate the `REG_NOTIFY_THREAD_AGNOSTIC` flag on systems that don’t support it? part 4](https://devblogs.microsoft.com/oldnewthing/20201224-00/?p=104599)
* [How can I emulate the `REG_NOTIFY_THREAD_AGNOSTIC` flag on systems that don’t support it? part 5](https://devblogs.microsoft.com/oldnewthing/20201225-00/?p=104602)
* [The history of passing a null pointer as the key name to `Reg­Open­Key­Ex`](https://devblogs.microsoft.com/oldnewthing/20210723-00/?p=105479)
* [On the failed unrealized promise of `Reg­Override­Predef­Key`](https://devblogs.microsoft.com/oldnewthing/20231020-00/?p=108911) (i.e. don't use it.)


## Strings and Locales

* [`TEXT` vs. `_TEXT` vs. `_T`, and `UNICODE` vs. `_UNICODE`](https://devblogs.microsoft.com/oldnewthing/20040212-00/?p=40643)
* [The sad history of Unicode `printf`-style format specifiers in Visual C++](https://devblogs.microsoft.com/oldnewthing/20190830-00/?p=102823)
* [Nasty gotcha: `SetThreadUILanguage` cannot be used to restore the thread UI language](https://devblogs.microsoft.com/oldnewthing/20170908-00/?p=96965)
* [How can `CharUpper` and `CharLower` guarantee that the uppercase version of a string is the same length as the lowercase version?](https://devblogs.microsoft.com/oldnewthing/20200804-00/?p=104040) (use `LCMapStringEx()` in any new code)
* [Is there a code page that matches ASCII and can round trip arbitrary bytes through Unicode?](https://devblogs.microsoft.com/oldnewthing/20200831-00/?p=104142)
* [A consequence of being the first to adopt a standard is that you may end up being the only one to adopt it: The sad story of Korean jamo](https://devblogs.microsoft.com/oldnewthing/20201009-00/?p=104351)
* [The `activeCodePage` manifest element can be used for more than just setting UTF-8 as the active code page](https://devblogs.microsoft.com/oldnewthing/20220531-00/?p=106697)
* [Feel free to stop using `IMultiLanguage2::DetectInputCodepage`](https://devblogs.microsoft.com/oldnewthing/20221003-00/?p=107241)
* [On the proper care and feeding of the enigmatic `Get­Distance­Of­Closest­Language­In­List` function](https://devblogs.microsoft.com/oldnewthing/20230320-00/?p=107949)
* [How can I get `WideCharToMultiByte` to convert strings encoded in UTF-16BE?](https://devblogs.microsoft.com/oldnewthing/20231005-00/?p=108854)


## NT Services

* [Calling `ShutdownBlockReasonCreate` from my service doesn't stop the user from shutting down](https://devblogs.microsoft.com/oldnewthing/20151002-00/?p=91461)
* [What does it mean when my attempt to stop a Windows NT service fails with `ERROR_BROKEN_PIPE`?](https://devblogs.microsoft.com/oldnewthing/20190405-00/?p=102389)
* [How can I configure my Windows NT service to autostart when the system gains Internet access?](https://devblogs.microsoft.com/oldnewthing/20200227-00/?p=103494)
* [On the confusing names for the Windows service SID types](https://devblogs.microsoft.com/oldnewthing/20231004-00/?p=108849)


## Uncategorized

* [How do I determine the processor's cache line size?](https://devblogs.microsoft.com/oldnewthing/20091208-01/?p=15733) (`GetLogicalProcessorInformation()`)
* [Why are structure sizes checked strictly?](https://devblogs.microsoft.com/oldnewthing/20031212-00/?p=41523)
* [What's the difference between `CreateMenu` and `CreatePopupMenu`?](https://devblogs.microsoft.com/oldnewthing/20031230-00/?p=41273)
* [Why are `HANDLE` return values so inconsistent?](https://devblogs.microsoft.com/oldnewthing/20040302-00/?p=40443)
* [How to retrieve text under the cursor (mouse pointer)](https://devblogs.microsoft.com/oldnewthing/20040423-00/?p=39663)
* [How to detect programmatically whether you are running on 64-bit Windows](https://devblogs.microsoft.com/oldnewthing/20050201-00/?p=36553)
* [A timed context menu](https://devblogs.microsoft.com/oldnewthing/20050307-00/?p=36263)
* [The importance of passing the `WT_EXECUTELONGFUNCTION` flag to `QueueUserWorkItem`](https://devblogs.microsoft.com/oldnewthing/20050722-15/?p=34843)
* [If your callback fails, it's your responsibility to set the error code](https://devblogs.microsoft.com/oldnewthing/20060123-12/?p=32573)
* [The double-click time tells the window manager how good your reflexes are](https://devblogs.microsoft.com/oldnewthing/20080423-00/?p=22623)
* [The cursor isn't associated with a window or a window class; it's associated with a thread group](https://devblogs.microsoft.com/oldnewthing/20110207-00/?p=11563)
* [Menu item states are not reliable until they are shown because they aren't needed until then](https://devblogs.microsoft.com/oldnewthing/20110805-00/?p=9963)
* [How can I display a live screenshot of a piece of another application?](https://devblogs.microsoft.com/oldnewthing/20130513-00/?p=4393)
* [Converting from a UTC-based `SYSTEMTIME` directly to a local-time-based `SYSTEMTIME`](https://devblogs.microsoft.com/oldnewthing/20140307-00/?p=1573)
* [Programmatically uploading a file to an FTP site](https://devblogs.microsoft.com/oldnewthing/20140310-00/?p=1563)
* [How can you use both versions 5 and 6 of the common controls within the same module?](https://devblogs.microsoft.com/oldnewthing/20140508-00/?p=1043)
* [How can I tell if Windows Update is waiting for the system to reboot?](https://devblogs.microsoft.com/oldnewthing/20150921-00/?p=91551)
* [How do I call `SetTimer` with a timer ID that is guaranteed not to conflict with any other timer ID?](https://devblogs.microsoft.com/oldnewthing/20150924-00/?p=91521)
* [A window can’t have two timers with the same ID, so how do I assign an ID that nobody else is using?](https://devblogs.microsoft.com/oldnewthing/20191009-00/?p=102974)
* [What does it mean when a display change is temporary?](https://devblogs.microsoft.com/oldnewthing/20080104-00/?p=23923)
* [How do I obtain the comment for a share?](https://devblogs.microsoft.com/oldnewthing/20151005-00/?p=91441)
* [How accurate are the various Windows time-querying functions?](https://devblogs.microsoft.com/oldnewthing/20170921-00/?p=97057)
* [How can I detect whether the user is logging off?](https://devblogs.microsoft.com/oldnewthing/20180705-00/?p=99175)
* [Why are timer IDs and dialog control IDs 64-bit values on 64-bit Windows? Did you really expect people to create more than 4 billion timers or dialog controls?](https://devblogs.microsoft.com/oldnewthing/20191010-00/?p=102978)
* [If you suppress GDI+ background thread, then you are expected to pump messages yourself](https://devblogs.microsoft.com/oldnewthing/20191029-00/?p=103033)
* [If one program blocks shutdown, then *all* programs block shutdown](https://devblogs.microsoft.com/oldnewthing/20200414-00/?p=103671) (`WM_QUERY­END­SESSION`, `WM_END­SESSION`)
* [When I ask the `GetIpAddrTable` function to sort the results, how are they sorted?](https://devblogs.microsoft.com/oldnewthing/20200415-00/?p=103673)
* [How can I detect that the system is no longer showing a UAC prompt?](https://devblogs.microsoft.com/oldnewthing/20200429-00/?p=103715) (`EVENT_SYSTEM_DESKTOP­SWITCH`)
* [How can I get the number of processors in the system, when there are more than 64?](https://devblogs.microsoft.com/oldnewthing/20200824-00/?p=104116)
* [Why are some system functions exported as stubs instead as forwarders?](https://devblogs.microsoft.com/oldnewthing/20200826-00/?p=104125)
* [How can I check whether the user has disconnected from the session?](https://devblogs.microsoft.com/oldnewthing/20201202-00/?p=104504)
* [Why does `PF_VIRT_FIRMWARE_ENABLED` return false even when virtualization is enabled in the firmware?](https://devblogs.microsoft.com/oldnewthing/20201216-00/?p=104550)
* [How can I convert between IANA time zones and Windows registry-based time zones?](https://devblogs.microsoft.com/oldnewthing/20210527-00/?p=105255)
* [The focus rectangle says, “I’m not orange. I’m just drawn that way.”](https://devblogs.microsoft.com/oldnewthing/20211102-00/?p=105866)
* [Why does the precise point at which I get a stack overflow exception change from run to run?](https://devblogs.microsoft.com/oldnewthing/20211216-00/?p=106038) (structured exception handling aka SEH)
* [How do I programmatically reposition monitors in a multiple-monitor system?](https://devblogs.microsoft.com/oldnewthing/20211222-00/?p=106048) (`ChangeDisplaySettingsEx()`)
* [How do I upgrade a 32-bit tick count to a 64-bit one?](https://devblogs.microsoft.com/oldnewthing/20220107-00/?p=106130)
* [The error code you get might not be the one you want](https://devblogs.microsoft.com/oldnewthing/20220119-00/?p=106176)
* [How can I find out which processor architectures are supported via emulation by the current system?](https://devblogs.microsoft.com/oldnewthing/20220209-00/?p=106239)
* [How can I detect whether the system has a keyboard attached? On the `GetRawInputDeviceList` function](https://devblogs.microsoft.com/oldnewthing/20220302-00/?p=106303)
* [Filtering out fake keyboards from the `GetRawInputDeviceList` function](https://devblogs.microsoft.com/oldnewthing/20220303-00/?p=106306)
* [How expensive is `PssCaptureSnapshot`? How fast is it? How much memory does it consume?](https://devblogs.microsoft.com/oldnewthing/20220314-00/?p=106346)
* [What is the `CreateExplorerShellUnelevatedTask` scheduled task?](https://devblogs.microsoft.com/oldnewthing/20220524-00/?p=106682)
* [Under what conditions can I modify the memory that I received in the form a `STGMEDIUM`?](https://devblogs.microsoft.com/oldnewthing/20220701-00/?p=106817)
* [Is it true that raising a structured exception from a structured exception handler terminates the process?](https://devblogs.microsoft.com/oldnewthing/20221020-00/?p=107303)
* [Why are many Windows user interface elements positioned at multiples of 4 or 8 pixels?](https://devblogs.microsoft.com/oldnewthing/20221025-00/?p=107318) (DPI, `DEVICE_SCALE_FACTOR`)
* [A history of the `fd_set`, `FD_SETSIZE`, and how it relates to WinSock](https://devblogs.microsoft.com/oldnewthing/20221102-00/?p=107343)
* [How can I detect programmatically whether Windows is an N or KN version?](https://devblogs.microsoft.com/oldnewthing/20221229-00/?p=107623)
* [How should I interpret the various values of `NLM_CONNECTIVITY`?](https://devblogs.microsoft.com/oldnewthing/20230112-00/?p=107700)
* [How can I find out the last time a user logged on from C++?](https://devblogs.microsoft.com/oldnewthing/20230622-00/?p=108369)
* [How can I specify icons for my app to use on the Start menu in high contrast mode?](https://devblogs.microsoft.com/oldnewthing/20240104-00/?p=109239)
* [How can I add an environment variable to a process launched via `Shell­Execute­Ex` or `IContext­Menu`?](https://devblogs.microsoft.com/oldnewthing/20240131-00/?p=109342)
* [Functions that return the size of a required buffer generally return upper bounds, not tight bounds](https://devblogs.microsoft.com/oldnewthing/20240214-00/?p=109400)
