![Last Update](https://img.shields.io/badge/Last_Update-Jan_11,_2020-brightgreen)

# The Old New Win32API

This page provides list of links to subset of posts of Raymond Chen's famous 
blog **[The Old New Thing](https://devblogs.microsoft.com/oldnewthing/)**. The
subset is limited mainly to Win32API and some COM-related stuff. 

**Disclaimer:** I am not claiming authorship of any linked contents. This is
only about hopefully useful organization of the great articles Raymond has
written over the years.

The reason why I manage this page is that it often provides information which
is missing on MSDN or which is described there in a cryptic way, and also 
because the blog is not easily searchable. 

The links here are categorized by their topic instead of a chronological order.
Sometimes, when appropriate, a single post may be put into multiple categories.

In some (quite rare) cases, links to other sources are included if they are
found useful.


## Table of Contents

* [Processes and Threads](#processes-and-threads)
  * [Processes](#processes)
  * [Threads](#threads)
  * [Thread Pools](#thread-pools)
  * [Thread Affinity of Objects](#thread-affinity-of-objects)
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
  * [Other Messages](#other-messages)
* [GDI](#gdi)
  * [Brushes](#brushes)
  * [DIB](#dib)
  * [`LockWindowUpdate()`](#lockwindowupdate)
  * [Painting Standard Elements](#painting-standard-elements)
  * [`UXTHEME.DLL`](#uxthemedll)
  * [Multiple Monitors](#multiple-monitors)
* [Accessibility](#accessibility)
* [COM](#com)
  * [COM Apartments](#com-apartments)
  * [COM Marshaling](#com-marshaling)
  * [COM Initialization](#com-initialization)
  * [COM Error Handling](#com-error-handling)
  * [GUIDs](#guids)
  * [COM Strings](#com-strings)
  * [COM Variants](#com-variants)
  * [`IUnknown`](#iunknown)
  * [`IMoniker`](#imoniker)
  * [`IContextMenu`](#icontextmenu)
  * [`IMultiLanguage`](#imultilanguage)
  * [`INamespaceWalk`](#inamespacewalk)
  * [Clipboard](#clipboard)
  * [Drag and Drop](#drag-and-drop)
  * [Enumeration](#enumeration)
  * [Shell](#shell)
  * [Uncategorized COM Stuff](#uncategorized-com-stuff)
* [Memory](#memory)
* [Input and Output](#input-and-output)
  * [Files and Directories](#files-and-directories)
  * [ACL](#acl)
* [Security Permissions, Attributes and Identifiers](#security-permissions-attributes-and-identifiers)
* [Registry](#registry)
* [Locale](#locale)
* [NT Services](#nt-services)
* [Uncategorized](#uncategorized)

## Processes and Threads

### Processes
* [`CreateProcess` does not wait for the process to start](https://devblogs.microsoft.com/oldnewthing/20050119-00/?p=36663)
* [Why does the `CreateProcess` function modify its input command line?](https://devblogs.microsoft.com/oldnewthing/20090601-00/?p=18083)
* [Disabling the program crash dialog](https://devblogs.microsoft.com/oldnewthing/20040727-00/?p=38323)
* [How do I pass a lot of data to a process when it starts up?](https://devblogs.microsoft.com/oldnewthing/20031211-00/?p=41543)
* [What was the purpose of the `hPrevInstance` parameter to `WinMain`?](https://devblogs.microsoft.com/oldnewthing/20040615-00/?p=38873)
* [Is `RunAsInvoker` a secret, even higher UAC setting?](https://devblogs.microsoft.com/oldnewthing/20161117-00/?p=94735)
* [How do I prevent a child process from displaying the Windows Error Reporting dialog?](https://devblogs.microsoft.com/oldnewthing/20160204-00/?p=92972)
* [How is it that `WriteProcessMemory` succeeds in writing to read-only memory?](https://devblogs.microsoft.com/oldnewthing/?p=100415)
* [Is it a good idea to let `WriteProcessMemory` manage the page protection for me?](https://devblogs.microsoft.com/oldnewthing/20190729-00/?p=102737)
* [How can I launch an unelevated process from my elevated process, redux](https://devblogs.microsoft.com/oldnewthing/20190425-00/?p=102443)

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

### Thread Pools
* [What exactly does the `msWindowLength` parameter to `SetThreadpoolTimer` mean?](https://devblogs.microsoft.com/oldnewthing/20160914-00/?p=94315)
* [What’s the difference between `CreateTimerQueueTimer` and `SetThreadpoolTimer`?](https://devblogs.microsoft.com/oldnewthing/20180308-00/?p=98185)
* [How to avoid accessing freed memory when canceling a thread pool callback](https://devblogs.microsoft.com/oldnewthing/20180502-00/?p=98655)
* [Avoiding deadlocks when cancelling a thread pool callback, part 1: External callback data](https://devblogs.microsoft.com/oldnewthing/20180503-00/?p=98665)
* [Avoiding deadlocks when cancelling a thread pool callback, part 2: Referring back to the containing object](https://devblogs.microsoft.com/oldnewthing/20180504-00/?p=98675)

### Thread Affinity of Objects
* [Thread affinity of user interface objects, part 1: Window handles](https://devblogs.microsoft.com/oldnewthing/20051010-09/?p=33843)
* [Thread affinity of user interface objects, part 2: Device contexts](https://devblogs.microsoft.com/oldnewthing/20051011-10/?p=33823)
* [Thread affinity of user interface objects, part 3: Menus, icons, cursors, and accelerator tables](https://devblogs.microsoft.com/oldnewthing/20051012-00/?p=33803)
* [Thread affinity of user interface objects, part 4: GDI objects and other notes on affinity](https://devblogs.microsoft.com/oldnewthing/20051013-11/?p=33783)
* [Thread affinity of user interface objects, part 5: Object clean-up](https://devblogs.microsoft.com/oldnewthing/20051014-19/?p=33763)
* [Thread affinity of user interface objects: Addendum](https://devblogs.microsoft.com/oldnewthing/20121109-00/?p=6133)

### Fibers
* [What happens to the fibers which ran on a thread when the thread exits?](https://devblogs.microsoft.com/oldnewthing/20100225-00/?p=14813)
* [It's fine to use fibers, but everybody has to be on board with the plan](https://devblogs.microsoft.com/oldnewthing/20100226-00/?p=14793)
* [Fibers aren’t useful for much any more; there’s just one corner of it that remains useful for a reason unrelated to fibers](https://devblogs.microsoft.com/oldnewthing/20191011-00/?p=102989)

## Synchronization

* [Understanding the consequences of `WAIT_ABANDONED`](https://devblogs.microsoft.com/oldnewthing/20050912-14/?p=34253)
* [Windows keyed events, critical sections, and new Vista synchronization features](http://joeduffyblog.com/2006/11/28/windows-keyed-events-critical-sections-and-new-vista-synchronization-features/)
* [Combining the work queue of distinct events, order not important, with an auto-reset event](https://devblogs.microsoft.com/oldnewthing/20170616-00/?p=96405)
* [How fair are SRW locks, particularly when there are both readers and writers?](https://devblogs.microsoft.com/oldnewthing/20170705-00/?p=96535)

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
* [The format of bitmap resources](https://devblogs.microsoft.com/oldnewthing/20091211-00/?p=15693)
* [The format of icon resources](https://devblogs.microsoft.com/oldnewthing/20120720-00/?p=7083)
* [The evolution of the ICO file format, part 1: Monochrome beginnings](https://devblogs.microsoft.com/oldnewthing/20101018-00/?p=12513)
* [The evolution of the ICO file format, part 2: Now in color!](https://devblogs.microsoft.com/oldnewthing/20101019-00/?p=12503)
* [The evolution of the ICO file format, part 3: Alpha-blended images](https://devblogs.microsoft.com/oldnewthing/20101021-00/?p=12483)
* [The evolution of the ICO file format, part 4: PNG images](https://devblogs.microsoft.com/oldnewthing/20101022-00/?p=12473)

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
* [How can I use `WS_CLIP­CHILDREN` and still be able to draw a control with a transparent background?](https://devblogs.microsoft.com/oldnewthing/20180926-00/?p=99825)

### Window Classes
* [What is the `HINSTANCE` passed to `CreateWindow` and `RegisterClass` used for?](https://devblogs.microsoft.com/oldnewthing/20050418-59/?p=35873)
* [Using the wrong `HINSTANCE` in `RegisterClass` is like identity theft](https://devblogs.microsoft.com/oldnewthing/20110715-00/?p=10133)
* [Changing a window class affects all windows which belong to that class](https://devblogs.microsoft.com/oldnewthing/20060227-12/?p=32133)
* [What does `CS_SAVEBITS` do?](https://devblogs.microsoft.com/oldnewthing/20060428-00/?p=31373)
* [What does the `CS_OWNDC` class style do?](https://devblogs.microsoft.com/oldnewthing/20060601-06/?p=31003)
* [What does the `CS_CLASSDC` class style do?](https://devblogs.microsoft.com/oldnewthing/20060602-00/?p=30993)
* [Modifying the `CS_NOCLOSE` style does affect all windows of the class, just not necessarily in an immediately noticeable way](https://devblogs.microsoft.com/oldnewthing/20150305-00/?p=44533)
* [Why does `PrintWindow` hate `CS_PARENTDC`? Because EVERYBODY hates `CS_PARENTDC`!](https://devblogs.microsoft.com/oldnewthing/20120604-00/?p=7463)
* [Why does `PrintWindow` hate CS_`PARENTDC`? redux](https://devblogs.microsoft.com/oldnewthing/20140410-00/?p=1283)
* [Safer subclassing](https://devblogs.microsoft.com/oldnewthing/20031111-00/?p=41883)
* [Private classes, superclassing, and global subclassing](https://devblogs.microsoft.com/oldnewthing/20100215-00/?p=14943)
* [What makes `RealGetWindowClass` so much more real than `GetClassName`?](https://devblogs.microsoft.com/oldnewthing/20101231-00/?p=11863)

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

### Dialogs
* [Why can't I create my dialog box? Rookie mistake #1](https://devblogs.microsoft.com/oldnewthing/?p=28123)
* [Why can't I create my dialog box? Rookie mistake #2](https://devblogs.microsoft.com/oldnewthing/20070207-04/?p=28113)
* [If I have a modeless dialog box with custom accelerators, which should I call first: `IsDialogMessage` or `TranslateAccelerator`](https://devblogs.microsoft.com/oldnewthing/20160818-00/?p=94115)
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
* [Why are dialog boxes initially created hidden?](https://devblogs.microsoft.com/oldnewthing/20040311-00/?p=40303)
* [What's the deal with the `DS_SHELLFONT` flag?](https://devblogs.microsoft.com/oldnewthing/20050204-00/?p=36523)
* [Why does `DS_SHELLFONT = DS_FIXEDSYS | DS_SETFONT`?](https://devblogs.microsoft.com/oldnewthing/20050207-00/?p=36513)
* [How to set focus in a dialog box](https://devblogs.microsoft.com/oldnewthing/20040802-00/?p=38283)
* [Never leave focus on a disabled control](https://devblogs.microsoft.com/oldnewthing/20040804-00/?p=38243)
* [A subtlety in restoring previous window position](https://devblogs.microsoft.com/oldnewthing/20050314-00/?p=36203)
* [Things you already know: How do I wait until my dialog box is displayed before doing something?](https://devblogs.microsoft.com/oldnewthing/20060922-03/?p=29623)
* [Gentle reminder: On a dialog box, do not give OK and Cancel accelerators](https://devblogs.microsoft.com/oldnewthing/20080508-00/?p=22403)
* [What does `TranslateAccelerator` do?](https://devblogs.microsoft.com/oldnewthing/20080523-00/?p=22203)
* [Why are accelerators for hidden controls still active?](https://devblogs.microsoft.com/oldnewthing/?p=22113)
* [Why doesn't the `TAB` key work on controls I've marked as `WS_TABSTOP`?](https://devblogs.microsoft.com/oldnewthing/20100930-00/?p=12683)
* [You can't use the `WM_USER` message in a dialog box](https://devblogs.microsoft.com/oldnewthing/20121024-00/?p=6263)
* [How can I make a dialog box right-to-left at runtime?](https://devblogs.microsoft.com/oldnewthing/20181122-00/?p=100295)

### Nested and Embedded Dialogs
* [What is the `DS_CONTROL` style for?](https://devblogs.microsoft.com/oldnewthing/20040730-00/?p=38293)
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

### Control Navigation
* [Using the `TAB` key to navigate in non-dialogs](https://devblogs.microsoft.com/oldnewthing/20031021-00/?p=42083)
* [Using the `TAB` key to navigate in non-dialogs, redux](https://devblogs.microsoft.com/oldnewthing/20131009-00/?p=2983)
* [Managing the UI state of accelerators and focus rectangles](https://devblogs.microsoft.com/oldnewthing/20050503-00/?p=35723)
* [Custom navigation in dialog boxes, redux](https://devblogs.microsoft.com/oldnewthing/20100222-00/?p=14863)
* [Dialog boxes return focus to the control that had focus when you last switched away; how do I get in on that action for my own windows?](https://devblogs.microsoft.com/oldnewthing/20140521-00/?p=943)

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

## Controls

* [Just because you're a control doesn't mean that you're necessarily inside a dialog box](https://devblogs.microsoft.com/oldnewthing/20070820-00/?p=25513)

### Animation Controls
* [Limitations of the shell animation control](https://devblogs.microsoft.com/oldnewthing/20050216-00/?p=36433)
* [Why does the version 6 animation control not use a background thread?](https://devblogs.microsoft.com/oldnewthing/?p=31883)

### Buttons
* [What's the `BS_PUSHLIKE` button style for?](https://devblogs.microsoft.com/oldnewthing/20070921-00/?p=25023) (Don't use, it's completely obsolete nowadays. Use check box or radio button instead.)

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

### Static Controls
* [When will the static control automatically delete the image loaded into it, and when is it the responsibility of the application?](https://devblogs.microsoft.com/oldnewthing/20140219-00/?p=1713)

### Tab Controls
* [How should I create controls on my dialog box that has a tab control?](https://devblogs.microsoft.com/oldnewthing/20191015-00/?p=102996)

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
[Adding a `Ctrl`+arrow accelerator for moving the trackbar by just one unit, part 1: Initial plunge](https://devblogs.microsoft.com/oldnewthing/20181023-00/?p=100035)
[Adding a `Ctrl`+arrow accelerator for moving the trackbar by just one unit, part 2: Second try](https://devblogs.microsoft.com/oldnewthing/20181024-00/?p=100045)
[How do I prevent users from using the mouse to drag the trackbar thumb to positions that aren’t multiples of five? Part 1: Reframe the problem](https://devblogs.microsoft.com/oldnewthing/20181025-00/?p=100055)
[How do I prevent users from using the mouse to drag the trackbar thumb to positions that aren’t multiples of five? Part 2: Nudging the thumb position](https://devblogs.microsoft.com/oldnewthing/20181026-00/?p=100065)

### Tree-List Views
* [The `TVS_CHECKBOXES` style is quirky, which is a polite way of saying that it is crazy](https://devblogs.microsoft.com/oldnewthing/20171127-00/?p=97465)
* [Beware of the leaked image list when using the `TVS_CHECKBOXES` style](https://devblogs.microsoft.com/oldnewthing/20171128-00/?p=97475)
* [Creating tree view check boxes manually: A simple state image list](https://devblogs.microsoft.com/oldnewthing/20171129-00/?p=97485)
* [Creating tree view check boxes manually: Responding to clicks](https://devblogs.microsoft.com/oldnewthing/20171130-00/?p=97495)
* [Creating tree view check boxes manually: Themed check boxes](https://devblogs.microsoft.com/oldnewthing/20171201-00/?p=97505)
* [Tree view check boxes: A sordid history](https://devblogs.microsoft.com/oldnewthing/20171204-00/?p=97515)
* [Tree view check boxes: The extended check box states](https://devblogs.microsoft.com/oldnewthing/20171205-00/?p=97525)

## Processing of Messages

* [Which message numbers belong to whom?](http://devblogs.com/b/oldnewthing/archive/2003/12/02/55914.aspx)
* [The various ways of sending a message](http://devblogs.com/b/oldnewthing/archive/2004/11/19/266664.aspx)
* [Broadcasting user-defined messages](http://devblogs.com/b/oldnewthing/archive/2004/05/05/126427.aspx)
* [When can a thread receive window messages?](http://devblogs.com/b/oldnewthing/archive/2004/06/08/150929.aspx)
* [What's the difference between `GetKeyState` and `GetAsyncKeyState`?](http://devblogs.com/b/oldnewthing/archive/2004/11/30/272262.aspx)
* [Thread messages are eaten by modal loops](http://devblogs.com/b/oldnewthing/archive/2005/04/26/412116.aspx)
* [Rescuing thread messages from modal loops via message filters](http://devblogs.com/b/oldnewthing/archive/2005/04/28/412574.aspx)
* [The dangers of filtering window messages](http://devblogs.com/b/oldnewthing/archive/2005/02/09/369804.aspx)
* [You can't simulate keyboard input with `PostMessage`](http://devblogs.com/b/oldnewthing/archive/2005/05/30/423202.aspx)
* [Pumping messages while waiting for a period of time](http://devblogs.com/b/oldnewthing/archive/2006/01/26/517849.aspx)
* [In pursuit of the message queue](http://devblogs.com/b/oldnewthing/archive/2006/02/21/536055.aspx)
* [No, really, you need to pass all unhandled messages to `DefWindowProc`](http://devblogs.com/b/oldnewthing/archive/2006/04/25/583093.aspx)
* [Even if you have code to handle a message, you're allowed to call `DefWindowProc`, because you were doing that anyway after all](http://devblogs.com/b/oldnewthing/archive/2009/01/05/9274857.aspx)
* [What were `Get/SetMessageExtraInfo` ever used for?](http://devblogs.com/b/oldnewthing/archive/2010/11/29/10097548.aspx)
* [Why is `GetWindowLongPtr` returning a garbage value on 64-bit Windows?](http://devblogs.com/b/oldnewthing/archive/2013/12/26/10484683.aspx)
* [`TrackMouseEvent` tracks mouse events in your window, but only if the events belong to your window](http://devblogs.com/b/oldnewthing/archive/2010/12/06/10100644.aspx)
* [Don't forget to include the message queue in your lock hierarchy](http://devblogs.com/b/oldnewthing/archive/2011/04/18/10154966.aspx)
* [What happens to a sent message when `SendMessageTimeout` reaches its timeout?](http://devblogs.com/b/oldnewthing/archive/2011/09/15/10208975.aspx)
* [Why can't I `PostMessage` the `WM_COPYDATA` message, but I can `SendMessageTimeout` it with a tiny timeout?](http://devblogs.com/b/oldnewthing/archive/2011/09/16/10208976.aspx)
* [Even though mouse-move, paint, and timer messages are generated on demand, it's still possible for one to end up in your queue](http://devblogs.com/b/oldnewthing/archive/2013/05/23/10420741.aspx)
* [Posted messages are processed ahead of input messages, even if they were posted later](http://devblogs.com/b/oldnewthing/archive/2013/05/31/10422524.aspx)
* [What kind of messages can a message-only window receive?](https://devblogs.microsoft.com/oldnewthing/20171218-00/?p=97595)
* [If the prototypes of `DispatchMessageA` and `DispatchMessageW` are identical, why have both?](https://devblogs.microsoft.com/oldnewthing/20181101-00/?p=100105)
* [Those who do not understand the dialog manager are doomed to reimplement it, badly](http://devblogs.com/b/oldnewthing/archive/2007/06/27/3555596.aspx)

### Hooking
* [What is the `HINSTANCE` passed to `SetWindowsHookEx` used for?](http://devblogs.com/b/oldnewthing/archive/2005/04/25/411741.aspx)
* [How can I get notified when the cursor changes?](https://devblogs.microsoft.com/oldnewthing/20151116-00/?p=92091)
* [What does the thread parameter to `Set­Windows­Hook­Ex` actually mean?](https://devblogs.microsoft.com/oldnewthing/20180926-00/?p=99825)
* [Why does `SetFocus` fail without telling me why?](https://devblogs.microsoft.com/oldnewthing/20190614-00/?p=102593)

## Specific Messages

### Notifications
* [What's the difference between the `wParam` of the `WM_NOTIFY` message and the `idFrom` in the `NMHDR` structure.](http://devblogs.com/b/oldnewthing/archive/2013/12/04/10473637.aspx)
* [Restating the obvious about the `WM_COMMAND` message](http://devblogs.com/b/oldnewthing/archive/2006/03/02/542115.aspx)
* [Restating the obvious about the `WM_NOTIFY` message](http://devblogs.com/b/oldnewthing/archive/2009/08/21/9877791.aspx)

### Window Construction and Destruction
* [What is the difference between `WM_DESTROY` and `WM_NCDESTROY`?](http://devblogs.com/b/oldnewthing/archive/2005/07/26/443384.aspx)
* [How can I determine the reason why my window is closing?](https://devblogs.microsoft.com/oldnewthing/20190411-00/?p=102411) (`WM_CLOSE`)

### Window Geometry Messages
* [Use `WM_WINDOWPOSCHANGED` to react to window state changes](http://devblogs.com/b/oldnewthing/archive/2008/01/15/7113860.aspx)
* [Use `WM_WINDOWPOSCHANGING` to intercept window state changes](http://devblogs.com/b/oldnewthing/archive/2008/01/16/7123299.aspx)

### Window Painting Messages
* [Paint messages will come in as fast as you let them](http://devblogs.com/b/oldnewthing/archive/2011/12/19/10249000.aspx) (`WM_PAINT`)
* [What happens if I don't paint when I get a `WM_PAINT` message?](http://devblogs.com/b/oldnewthing/archive/2014/12/03/10577531.aspx)
* [What is the implementation of `WM_PRINTCLIENT`?](http://devblogs.com/b/oldnewthing/archive/2009/03/30/9517659.aspx)
* [There's a default implementation for `WM_SETREDRAW`, but you might be able to do better](http://devblogs.com/b/oldnewthing/archive/2011/01/24/10119211.aspx)
* [Speeding up adding items to a combobox or listbox](http://devblogs.com/b/oldnewthing/archive/2004/06/10/152612.aspx) (`WM_SETREDRAW`)
* [Using `WM_SETREDRAW` to speed up adding a lot of elements to a control](http://devblogs.com/b/oldnewthing/archive/2014/04/07/10514610.aspx)

### Window Focus Messages
* [`WM_KILLFOCUS` is the wrong time to do field validation](http://devblogs.com/b/oldnewthing/archive/2004/04/19/115912.aspx)
* [The dangers of playing focus games when handling a `WM_KILLFOCUS` message](http://devblogs.com/b/oldnewthing/archive/2005/08/08/448969.aspx)
* [Why doesn't the `MoveWindow` function generate the `WM_GETMINMAXINFO` message?](http://devblogs.com/b/oldnewthing/archive/2009/03/09/9466834.aspx)

### Keyboard Messages
* [How do I respond to the `WM_MENUCHAR` message?](https://devblogs.microsoft.com/oldnewthing/20171208-00/?p=97545)

### Mouse Messages
* [Why is there no `WM_MOUSEENTER` message?](http://devblogs.com/b/oldnewthing/archive/2003/10/13/55279.aspx)
* [Why do I get spurious `WM_MOUSEMOVE` messages?](http://devblogs.com/b/oldnewthing/archive/2003/10/01/55108.aspx)
* [Sure, I can get spurious `WM_MOUSEMOVE` messages, but why do they keep streaming in?](http://devblogs.com/b/oldnewthing/archive/2009/06/17/9763416.aspx)
* [How do I get mouse messages faster than `WM_MOUSEMOVE`?](http://devblogs.com/b/oldnewthing/archive/2012/03/14/10282406.aspx)
* [Logical consequences of the way Windows converts single-clicks into double-clicks](http://devblogs.com/b/oldnewthing/archive/2004/10/15/242761.aspx)
* [Implementing higher-order clicks](http://devblogs.com/b/oldnewthing/archive/2004/10/18/243925.aspx)
* [How slow do you have to slow-double-click for it to be a rename?](http://devblogs.com/b/oldnewthing/archive/2008/11/10/9056610.aspx)

### Dialog Messages
* [Those who do not understand the dialog manager are doomed to reimplement it, badly](http://devblogs.com/b/oldnewthing/archive/2007/06/27/3555596.aspx)
* [Managing the UI state of accelerators and focus rectangles](http://devblogs.com/b/oldnewthing/archive/2005/05/03/414317.aspx) (`WM_CHANGEUISTATE`, `WM_QUERYUISTATE` and `WM_UPDATEUISTATE`)
* [Untangling the confusingly-named `WM_UPDATEUISTATE` and `WM_CHANGEUISTATE` messages](http://devblogs.com/b/oldnewthing/archive/2013/05/16/10419105.aspx)
* [Who sends the initial `WM_UPDATEUISTATE` message?](http://devblogs.com/b/oldnewthing/archive/2013/05/17/10419502.aspx)
* [How can I prevent the keyboard focus rectangle from appearing on a control I created?](https://devblogs.microsoft.com/oldnewthing/20171206-00/?p=97526)
* [Other tricks with `WM_GETDLGCODE`](http://devblogs.com/b/oldnewthing/archive/2003/11/26/55872.aspx)
* [How do I prevent multi-line edit controls from eating the Enter key?](http://devblogs.com/b/oldnewthing/archive/2006/10/12/819674.aspx)
* [Why do `DLGC_WANTALLKEYS` and `DLGC_WANTMESSAGE` have the same value?](http://devblogs.com/b/oldnewthing/archive/2007/06/26/3532603.aspx)

### Other Messages
* [The dangers of messing with activation when handling a `WM_ACTIVATE` message](http://devblogs.com/b/oldnewthing/archive/2005/08/09/449437.aspx)
* [Why does my window get a `WM_ACTIVATE` message when it isn't active?](http://devblogs.com/b/oldnewthing/archive/2013/10/16/10456992.aspx)
* [A timed context menu](http://devblogs.com/b/oldnewthing/archive/2005/03/07/387044.aspx) (`WM_CANCELMODE`)
* [Pitfalls in handling the `WM_CONTEXTMENU` message](http://devblogs.com/b/oldnewthing/archive/2004/09/21/232369.aspx) (`WM_CONTEXTMENU`)
* [Why do I have to return this goofy value for `WM_DEVICECHANGE`?](http://devblogs.com/b/oldnewthing/archive/2003/12/05/55936.aspx) (`WM_DEVICECHANGE`)
* [Windows doesn't close windows when a user logs off; that's your call](http://devblogs.com/b/oldnewthing/archive/2008/04/21/8413175.aspx) (`WM_ENDSESSION`)
* [Once you return from the `WM_ENDSESSION` message, your process can be terminated at any time](http://devblogs.com/b/oldnewthing/archive/2013/06/27/10429232.aspx) (`WM_ENDSESSION`)
* [`WM_NCHITTEST` is for hit-testing, and hit-testing can happen for reasons other than the mouse being over your window](http://devblogs.com/b/oldnewthing/archive/2011/02/18/10131176.aspx)
* [How likely is it that a window will receive a `WM_NULL` message out of the blue?](https://devblogs.microsoft.com/oldnewthing/20170602-00/?p=96266) (`WM_NULL`)
* [Why is there a special `PostQuitMessage` function?](http://devblogs.com/b/oldnewthing/archive/2005/11/04/489028.aspx) (`WM_QUIT`)
* [How does `PostQuitMessage` know which thread to post the quit message to?](http://devblogs.com/b/oldnewthing/archive/2009/01/12/9306611.aspx) (`WM_QUIT`)
* [Who is responsible for destroying the font passed in the `WM_SETFONT` message?](http://devblogs.com/b/oldnewthing/archive/2008/09/12/8945692.aspx) (`WM_SETFONT`)
* [When I send a `WM_GETFONT` message to a window, why don't I get a font?](http://devblogs.com/b/oldnewthing/archive/2014/07/24/10544760.aspx) (`WM_GETFONT`)
* [If my `WM_TIMER` handler takes longer than the timer period, will my queue fill up with `WM_TIMER` messages?](http://devblogs.com/b/oldnewthing/archive/2014/12/04/10577881.aspx)
* [Killing a window timer prevents the `WM_TIMER` message from being generated for that timer, but it doesn't retroactively remove ones that were already generated](http://devblogs.com/b/oldnewthing/archive/2014/12/05/10578385.aspx)


## GDI

* [Why are `RECT`s endpoint-exclusive?](http://devblogs.com/b/oldnewthing/archive/2004/02/18/75652.aspx)
* [Can you create an information context for the display?](http://devblogs.com/b/oldnewthing/archive/2009/09/14/9894751.aspx)
* [What does the `CS_OWNDC` class style do?](http://devblogs.com/b/oldnewthing/archive/2006/06/01/612970.aspx)
* [What does the `CS_CLASSDC` class style do?](http://devblogs.com/b/oldnewthing/archive/2006/06/02/614235.aspx)
* [How do you detect "Large Fonts"?](http://devblogs.com/b/oldnewthing/archive/2004/07/14/182971.aspx) (DPI)
* [The effect of `SetCursor` lasts only until the next `SetCursor`](http://devblogs.com/b/oldnewthing/archive/2005/05/25/421707.aspx)
* [Drawing a monochrome bitmap with transparency](http://devblogs.com/b/oldnewthing/archive/2005/08/03/447131.aspx)
* [Let GDI do your RLE compression for you](http://devblogs.com/b/oldnewthing/archive/2009/04/08/9537051.aspx)
* [The mysterious stock bitmap: There's no way to summon it, but it shows up in various places](http://devblogs.com/b/oldnewthing/archive/2010/04/16/9996968.aspx)
* [Why is my icon being drawn at the wrong size when I call `DrawIcon`?](http://devblogs.com/b/oldnewthing/archive/2010/07/29/10043635.aspx)
* [You must flush GDI operations when switching between direct access and GDI access, and direct access includes other parts of GDI](http://devblogs.com/b/oldnewthing/archive/2010/09/23/10066473.aspx)
* [How do I get the dimensions of a cursor or icon?](http://devblogs.com/b/oldnewthing/archive/2010/10/20/10078140.aspx)
* [What are the dire consequences of not selecting objects out of my DC?](http://devblogs.com/b/oldnewthing/archive/2013/03/06/10399678.aspx)
* [Of what use is the `RDW_INTERNALPAINT` flag?](http://devblogs.com/b/oldnewthing/archive/2013/06/21/10427533.aspx)
* [Functions that return GDI regions rarely actually return regions](http://devblogs.com/b/oldnewthing/archive/2014/03/27/10511270.aspx)
* [Color-aware ClearType requires access to fixed background pixels, which is a problem if you don't know what the background pixels are, or if they aren't fixed](http://devblogs.com/b/oldnewthing/archive/2015/01/29/10589474.aspx)
* [What is the correct way of using `SaveDC` and `RestoreDC`?](https://devblogs.microsoft.com/oldnewthing/20170920-00/?p=97055)
* [How are `BitBlt` raster opcodes calculated?](https://devblogs.microsoft.com/oldnewthing/20180528-00/?p=98845)
* [Notes on `DrawText` and tab stops](https://devblogs.microsoft.com/oldnewthing/20181010-00/?p=99935)
* [Why doesn’t `GetTextExtentPoint` return the correct extent for strings containing tabs?](https://devblogs.microsoft.com/oldnewthing/20181012-00/?p=99955)
* [How can I extract the color from a solid color GDI brush?](https://devblogs.microsoft.com/oldnewthing/20190802-00/?p=102747)

### Brushes
* [The hollow brush](http://devblogs.com/b/oldnewthing/archive/2004/01/26/62991.aspx)
* [Other uses for bitmap brushes](http://devblogs.com/b/oldnewthing/archive/2003/10/09/55243.aspx)
* [What is the DC brush good for?](http://devblogs.com/b/oldnewthing/archive/2005/04/20/410031.aspx)

### DIB
* [A survey of the various ways of creating GDI bitmaps with predefined data](https://devblogs.microsoft.com/oldnewthing/20170331-00/?p=95875)
* [Blitting between color and monochrome DCs](http://devblogs.com/b/oldnewthing/archive/2006/11/14/1075571.aspx)
* [Manipulating the DIB color table for fun and profit](http://devblogs.com/b/oldnewthing/archive/2006/11/15/1081320.aspx)
* [Using DIB sections to perform bulk color mapping](http://devblogs.com/b/oldnewthing/archive/2006/11/16/1086835.aspx)
* [The fun and profit of manipulating the DIB color table can be done without having to modify it](http://devblogs.com/b/oldnewthing/archive/2009/07/14/9832544.aspx)
* [Separating the metadata from the DIB pixels: Precalculating the `BITMAPINFO`](http://devblogs.com/b/oldnewthing/archive/2009/07/15/9833677.aspx)
* [Separating the metadata from the DIB pixels: Changing the raster operation](http://devblogs.com/b/oldnewthing/archive/2009/07/16/9834856.aspx)
* [The disembodiment of DIBs from the DIB section](http://devblogs.com/b/oldnewthing/archive/2009/07/17/9836293.aspx)
* [What is the `hSection` parameter to `CreateDIBSection` for?](http://devblogs.com/b/oldnewthing/archive/2010/01/08/9945482.aspx)

### `LockWindowUpdate()`
* [What does `LockWindowUpdate` do?](http://devblogs.com/b/oldnewthing/archive/2007/02/19/1716211.aspx)
* [How is `LockWindowUpdate` meant to be used?](http://devblogs.com/b/oldnewthing/archive/2007/02/20/1726880.aspx)
* [With what operations is `LockWindowUpdate` meant to be used?](http://devblogs.com/b/oldnewthing/archive/2007/02/21/1735472.aspx)
* [With what operations is `LockWindowUpdate` not meant to be used?](http://devblogs.com/b/oldnewthing/archive/2007/02/22/1742084.aspx)
* [Final remarks on `LockWindowUpdate`](http://devblogs.com/b/oldnewthing/archive/2007/02/23/1747713.aspx)

### Painting Standard Elements
* [Rendering standard Windows elements](http://devblogs.com/b/oldnewthing/archive/2005/08/01/445998.aspx)
* [Rendering menu glyphs is slightly trickier](http://devblogs.com/b/oldnewthing/archive/2005/08/02/446605.aspx)
* [What states are possible in a `DRAWITEMSTRUCT` structure?](http://devblogs.com/b/oldnewthing/archive/2014/12/11/10580099.aspx)

### `UXTHEME.DLL`
* [`BeginBufferedPaint`: It's not just for buffered painting any more](http://devblogs.com/b/oldnewthing/archive/2011/05/20/10166505.aspx)
* [How do `IsThemeActive`, `IsAppThemed`, and `IsCompositionActive` differ?](http://devblogs.com/b/oldnewthing/archive/2011/05/26/10168421.aspx)
* [How do I get the tabbed dialog effect on my own custom tabbed dialog?](http://devblogs.com/b/oldnewthing/archive/2012/11/05/10365656.aspx)
* [How do I revert a control back to its default theme?](https://devblogs.microsoft.com/oldnewthing/20181115-00/?p=100225)

### Multiple Monitors
* [For better performance, set all your monitors to the same color format](http://devblogs.com/b/oldnewthing/archive/2010/02/08/9959494.aspx)
* [How do I get a handle to the primary monitor?](http://devblogs.com/b/oldnewthing/archive/2014/11/06/10570272.aspx)
* [Why does the primary monitor have (0,0) as its upper left coordinate?](http://devblogs.com/b/oldnewthing/archive/2010/08/20/10052248.aspx)
* [How do I get the color depth of the screen?](http://devblogs.com/b/oldnewthing/archive/2010/10/13/10075056.aspx)
* [How does the window manager adjust `ptMaxSize` and `ptMaxPosition` for multiple monitors?](http://devblogs.com/b/oldnewthing/archive/2015/05/01/10611357.aspx)

## Accessibility

* [Accessibility is not just for people with disabilities](https://devblogs.microsoft.com/oldnewthing/?p=30093)
* [How to retrieve text under the cursor (mouse pointer)](https://devblogs.microsoft.com/oldnewthing/20130408-00/?p=4733)
* [How do I set an accessible name on an unlabeled control?](https://devblogs.microsoft.com/oldnewthing/20111013-00/?p=9393)
* [How can I get notified when some other window is destroyed?](https://devblogs.microsoft.com/oldnewthing/20111026-00/?p=9263)
* [Using accessibility to monitor windows as they come and go](https://devblogs.microsoft.com/oldnewthing/20130325-00/?p=4863)
* [How can I write a program that monitors another window for a title change?](https://devblogs.microsoft.com/oldnewthing/20180601-00/?p=98895)

## COM

### COM Apartments
* [The dreaded "main" threading model](http://devblogs.com/b/oldnewthing/archive/2004/06/02/146671.aspx)
* [A slightly less brief introduction to COM apartments (but it’s still brief)](https://devblogs.microsoft.com/oldnewthing/20191125-00/?p=103135)
* [Yo dawg, I hear you like COM apartments, so I put a COM apartment in your COM apartment so you can COM apartment while you COM apartment](https://devblogs.microsoft.com/oldnewthing/20191126-00/?p=103140)
* [Setting up private COM contexts to allow yourself to unload cleanly](https://devblogs.microsoft.com/oldnewthing/20191127-00/?p=103153)
* [How do you get into a context via `IContext­Callback::Context­Callback`?](https://devblogs.microsoft.com/oldnewthing/20191128-00/?p=103157)
* [Using contexts to return to a COM apartment later](https://devblogs.microsoft.com/oldnewthing/20191129-00/?p=103162)
* [What do the output values from `CoGetApartmentType` mean?](https://devblogs.microsoft.com/oldnewthing/20180208-00/?p=97986)
* [User interface code + multi-threaded apartment = death](http://devblogs.com/b/oldnewthing/archive/2008/04/24/8420242.aspx)
* [Other problems traced to violating COM single-threaded apartment rules in the shell](http://devblogs.com/b/oldnewthing/archive/2007/10/19/5515428.aspx)

### COM Marshaling
* [What is COM marshaling and how do I use it?](http://devblogs.com/b/oldnewthing/archive/2015/10/20/10648886.aspx)
* [What are the rules for `CoMarshalInterThreadInterfaceInStream` and `CoGetInterfaceAndReleaseStream`?](devblogs.com/b/oldnewthing/archive/2015/10/21/10649190.aspx)
* [What are the rules for `CoMarshalInterface` and `CoUnmarshalInterface`?](http://devblogs.com/b/oldnewthing/archive/2015/10/22/10649480.aspx)
* [`CoGetInterfaceAndReleaseStream` does not mix with smart pointers](http://devblogs.com/b/oldnewthing/archive/2015/10/23/10649707.aspx)
* [The COM marshaller uses the COM task allocator to allocate and free memory](http://devblogs.com/b/oldnewthing/archive/2009/09/23/9898230.aspx)
* [Why do I get a `QueryInterface(IID_IMarshal)` and then nothing?](http://devblogs.com/b/oldnewthing/archive/2004/02/20/77120.aspx)

### COM Initialization
* [What does the `COINIT_SPEED_OVER_MEMORY` flag to `CoInitializeEx` do?](http://devblogs.com/b/oldnewthing/archive/2012/11/08/10366704.aspx)

### COM Error Handling
* [What happens to my COM server-side object when clients die unexpectedly?](http://devblogs.com/b/oldnewthing/archive/2014/04/09/10515424.aspx)
* [Why does COM require output pointers to be initialized even on failure?](http://devblogs.com/b/oldnewthing/archive/2009/12/31/9942465.aspx)
* [How do I convert an `HRESULT` to a Win32 error code?](http://devblogs.com/b/oldnewthing/archive/2006/11/03/942851.aspx)
* [Do not overload the `E_NOINTERFACE` error](http://devblogs.com/b/oldnewthing/archive/2006/12/08/1239911.aspx)

### GUIDs
* [What's the difference between `UuidFromString`, `IIDFromString`, `CLSIDFromString`, `GUIDFromString`...](http://devblogs.com/b/oldnewthing/archive/2015/10/15/10647906.aspx)
* [Why are there four functions for parsing strings into GUIDs, and why are they in three different DLLs?](https://devblogs.microsoft.com/oldnewthing/20160331-00/?p=93231)

### COM Strings
* [Why is there a `BSTR` cache anyway?](http://devblogs.com/b/oldnewthing/archive/2015/01/07/10584656.aspx)
* [Raymond’s complete guide to `HSTRING` semantics](https://devblogs.microsoft.com/oldnewthing/20160615-00/?p=93675)
* [What is the correct way of using the string buffer returned by the `WindowsPreallocateStringBuffer` function?](https://devblogs.microsoft.com/oldnewthing/20170913-00/?p=97015)

### COM Variants
* [What’s the difference between `VARIANT` and `VARIANTARG`?](https://devblogs.microsoft.com/oldnewthing/20171221-00/?p=97625)
* [Nasty gotcha: `VarCmp` vs `VariantCompare`](https://devblogs.microsoft.com/oldnewthing/20160218-00/?p=93051)
* [Why can’t `VarDateFromStr` parse back a Hungarian date that was generated by `VarBstrFromDate`?](https://devblogs.microsoft.com/oldnewthing/20161219-00/?p=94965)

### `IUnknown`
* [The layout of a COM object](http://devblogs.com/b/oldnewthing/archive/2004/02/05/68017.aspx)
* [Under what conditions will the `IUnknown::AddRef` method return 0?](http://devblogs.com/b/oldnewthing/archive/2015/03/12/10599631.aspx)
* [The ways people mess up `IUnknown::QueryInterface`](http://devblogs.com/b/oldnewthing/archive/2004/03/26/96777.aspx)
* [The ways people mess up `IUnknown::QueryInterface`, episode 2](http://devblogs.com/b/oldnewthing/archive/2009/09/25/9899238.aspx)
* [The ways people mess up `IUnknown::QueryInterface`, episode 3](http://devblogs.com/b/oldnewthing/archive/2009/10/07/9904040.aspx)
* [The ways people mess up `IUnknown::QueryInterface`, episode 4](http://devblogs.com/b/oldnewthing/archive/2011/08/11/10194658.aspx)
* [COM object destructors are very sensitive functions](http://devblogs.com/b/oldnewthing/archive/2005/09/27/474384.aspx)
* [Avoiding double-destruction when an object is released](http://devblogs.com/b/oldnewthing/archive/2005/09/28/474855.aspx)
* [The COM interface contract rules exist for a reason](http://devblogs.com/b/oldnewthing/archive/2005/11/01/487658.aspx)

### `IMoniker`
* [Pidls and monikers do roughly the same thing, just backwards](http://devblogs.com/b/oldnewthing/archive/2006/07/12/663365.aspx)

### `IContextMenu`
* [Why an object cannot be its own enumerator](http://devblogs.com/b/oldnewthing/archive/2004/03/22/93885.aspx)
* [How to host an `IContextMenu`, part 1 - Initial foray](http://devblogs.com/b/oldnewthing/archive/2004/09/20/231739.aspx)
* [How to host an `IContextMenu`, part 2 - Displaying the context menu](http://devblogs.com/b/oldnewthing/archive/2004/09/22/232836.aspx)
* [How to host an `IContextMenu`, part 3 - Invocation location](http://devblogs.com/b/oldnewthing/archive/2004/09/23/233376.aspx)
* [How to host an `IContextMenu`, part 4 - Key context](http://devblogs.com/b/oldnewthing/archive/2004/09/24/234113.aspx)
* [How to host an `IContextMenu`, part 5 - Handling menu messages](http://devblogs.com/b/oldnewthing/archive/2004/09/27/234739.aspx)
* [How to host an `IContextMenu`, part 6 - Displaying menu help](http://devblogs.com/b/oldnewthing/archive/2004/09/28/235242.aspx)
* [How to host an `IContextMenu`, part 7 - Invoking the default verb](http://devblogs.com/b/oldnewthing/archive/2004/09/30/236133.aspx)
* [How to host an `IContextMenu`, part 8 - Optimizing for the default command](http://devblogs.com/b/oldnewthing/archive/2004/10/01/236627.aspx)
* [How to host an `IContextMenu`, part 9 - Adding custom commands](http://devblogs.com/b/oldnewthing/archive/2004/10/04/237507.aspx)
* [How to host an `IContextMenu`, part 10 - Composite extensions - groundwork](http://devblogs.com/b/oldnewthing/archive/2004/10/06/238630.aspx)
* [How to host an `IContextMenu`, part 11 - Composite extensions - composition](http://devblogs.com/b/oldnewthing/archive/2004/10/07/239197.aspx)
* [Simplifying context menu extensions with `IExecuteCommand`](http://devblogs.com/b/oldnewthing/archive/2010/03/12/9977246.aspx)
* [How do I launch a file as if it were a text file, even though its extension is not `.txt`?](http://devblogs.com/b/oldnewthing/archive/2013/02/13/10393162.aspx)
* [Do not access the disk in your `IContextMenu` handler, no really, don't do it](http://devblogs.com/b/oldnewthing/archive/2011/10/03/10218997.aspx)
* [Sure, we do that: Context menu edition](http://devblogs.com/b/oldnewthing/archive/2012/05/16/10305605.aspx)
* [Psychic debugging: Why your `IContextMenu::InvokeCommand` doesn't get called even though you returned success from `IContextMenu::QueryContextMenu`](http://devblogs.com/b/oldnewthing/archive/2013/02/01/10390112.aspx)
* [Don’t forget to implement canonical names for verbs in your shell context menu extension](https://devblogs.microsoft.com/oldnewthing/20170302-00/?p=95635)

### `IMultiLanguage`
* [Converting between `LCID`s and RFC 1766 language codes](http://devblogs.com/b/oldnewthing/archive/2006/01/05/509642.aspx)

### `INamespaceWalk`
* [How can I control which parts of the shell namespace the `INamespaceWalk::Walk` operation will walk into?](https://devblogs.microsoft.com/oldnewthing/20171108-00/?p=97365)
* [How can I cancel the `INamespace­Walk::Walk` operation?](https://devblogs.microsoft.com/oldnewthing/20171109-00/?p=97375)
* [Cancelling the `INamespace­Walk::Walk` operation a little faster](https://devblogs.microsoft.com/oldnewthing/20171110-00/?p=97385)

### Clipboard
* [What happens when applications try to copy text by sending `Ctrl+C`](http://devblogs.com/b/oldnewthing/archive/2011/06/23/10178000.aspx)
* [How do I make it so that users can copy static text on a dialog box to the clipboard easily?](http://devblogs.com/b/oldnewthing/archive/2012/03/01/10275051.aspx)
* [What is the proper handling of `WM_RENDERFORMAT` and `WM_RENDERALLFORMATS`?](http://devblogs.com/b/oldnewthing/archive/2012/12/24/10380437.aspx)
* [Copying a file to the clipboard so you can paste it into Explorer or an email message or whatever](http://devblogs.com/b/oldnewthing/archive/2013/05/20/10419965.aspx)
* [Printing the contents of the clipboard as text to `stdout`](http://devblogs.com/b/oldnewthing/archive/2013/10/07/10454659.aspx)
* [Improving the performance of `CF_HDROP` by providing file attribute information](http://devblogs.com/b/oldnewthing/archive/2014/06/09/10532207.aspx)

### Drag and Drop
* [What a drag: Dragging text](http://devblogs.com/b/oldnewthing/archive/2008/03/11/8080077.aspx)
* [What a drag: Dragging a Uniform Resource Locator (URL)](http://devblogs.com/b/oldnewthing/archive/2008/03/12/8080101.aspx)
* [What a drag: Dragging a Uniform Resource Locator (URL) and text](http://devblogs.com/b/oldnewthing/archive/2008/03/13/8080135.aspx)
* [What a drag: Dragging a virtual file (`HGLOBAL` edition)](http://devblogs.com/b/oldnewthing/archive/2008/03/18/8080183.aspx)
* [What a drag: Dragging a virtual file (`IStream` edition)](http://devblogs.com/b/oldnewthing/archive/2008/03/19/8080215.aspx)
* [What a drag: Dragging a virtual file (`IStorage` edition)](http://devblogs.com/b/oldnewthing/archive/2008/03/20/8080229.aspx)
* [You can drag multiple virtual objects, you know](http://devblogs.com/b/oldnewthing/archive/2008/03/31/8344798.aspx)
* [Reading a contract from the other side: Simulating a drop](http://devblogs.com/b/oldnewthing/archive/2008/07/24/8768095.aspx)
* [Simulating a drop, part two](http://devblogs.com/b/oldnewthing/archive/2008/07/25/8770548.aspx)
* [What happens if I drag the mouse by exactly the amount specified by `SM_CXDRAG`?](http://devblogs.com/b/oldnewthing/archive/2010/03/04/9972520.aspx)
* [How do I accept files to be opened via `IDropTarget` instead of on the command line?](http://devblogs.com/b/oldnewthing/archive/2010/05/03/10006065.aspx)
* [How do I accept files to be opened via `IDropTarget` instead of on the command line? - bonus content](http://devblogs.com/b/oldnewthing/archive/2010/05/28/10016692.aspx)

### Enumeration
* [Using fibers to simplify enumerators, part 1: When life is easier for the enumerator](http://devblogs.com/b/oldnewthing/archive/2004/12/29/343664.aspx)
* [Using fibers to simplify enumerators, part 2: When life is easier for the caller](http://devblogs.com/b/oldnewthing/archive/2004/12/30/344281.aspx)
* [Using fibers to simplify enumerators, part 3: Having it both ways](http://devblogs.com/b/oldnewthing/archive/2004/12/31/344799.aspx)
* [Using fibers to simplify enumerators, part 4: Filtering](http://devblogs.com/b/oldnewthing/archive/2005/01/03/345800.aspx)
* [Using fibers to simplify enumerators, part 5: Composition](http://devblogs.com/b/oldnewthing/archive/2005/01/04/346274.aspx)

### Shell
* [When does `SHLoadInProc` unload a DLL?](http://devblogs.com/b/oldnewthing/archive/2004/06/28/167800.aspx)
* [What does `SHGFI_USEFILEATTRIBUTES` mean?](http://devblogs.com/b/oldnewthing/archive/2004/06/01/145428.aspx)
* [What's the difference between `SHGetMalloc`, `SHAlloc`, `CoGetMalloc`, and `CoTaskMemAlloc`](http://devblogs.com/b/oldnewthing/archive/2004/07/05/173226.aspx)
* [Querying information from an Explorer window](http://devblogs.com/b/oldnewthing/archive/2004/07/20/188696.aspx)
* [Execute a file as if it were a program, even though its extension is not `EXE`](http://devblogs.com/b/oldnewthing/archive/2014/02/10/10497960.aspx)
* [What does the `SEE_MASK_UNICODE` flag in `ShellExecuteEx` actually do?](http://devblogs.com/b/oldnewthing/archive/2014/02/27/10503519.aspx)
* [Simple things you can do with the `ShellExecuteEx` function](http://devblogs.com/b/oldnewthing/archive/2004/11/26/270710.aspx)
* [What were `ShellExecute` hooks designed for?](http://devblogs.com/b/oldnewthing/archive/2008/09/10/8938051.aspx)
* [Why does `ShellExecute` return `SE_ERR_ACCESSDENIED` for nearly everything?](http://devblogs.com/b/oldnewthing/archive/2012/10/18/10360604.aspx)
* [How do I `ShellExecute` a file, but with a specific program instead of the default program?](https://devblogs.microsoft.com/oldnewthing/20171220-00/?p=97615)
* [What is the difference between `CSIDL_DESKTOP` and `CSIDL_DESKTOPDIRECTORY`?](http://devblogs.com/b/oldnewthing/archive/2009/07/30/9852685.aspx)
* [`SHCIDS_CANONICALONLY` is the moral equivalent in the shell namespace of the Unicode ordinal comparison](http://devblogs.com/b/oldnewthing/archive/2009/08/07/9859707.aspx)
* [Don't forget to double-null-terminate those strings you pass to `SHFileOperation`](http://devblogs.com/b/oldnewthing/archive/2010/02/18/9965469.aspx)
* [Why does `SHFileOperation` have internal error codes for DVD?](http://devblogs.com/b/oldnewthing/archive/2010/03/22/9982671.aspx)
* [Why do non-folders in my shell namespace extension show up in the folder tree view?](http://devblogs.com/b/oldnewthing/archive/2010/04/02/9989235.aspx)
* [`SHAutoComplete` giveth, and `SHAutoComplete` taketh away](http://devblogs.com/b/oldnewthing/archive/2010/05/21/10013613.aspx)
* [What is the `lpClass` member of `SHELLEXECUTEINFO` used for?](http://devblogs.com/b/oldnewthing/archive/2010/07/01/10033224.aspx)
* [Some known folders cannot be moved, but others can, and you'll just have to accept that](http://devblogs.com/b/oldnewthing/archive/2010/08/06/10046812.aspx)
* [One possible reason why `ShellExecute` returns `SE_ERR_ACCESSDENIED` and `ShellExecuteEx` returns `ERROR_ACCESS_DENIED`](http://devblogs.com/b/oldnewthing/archive/2010/11/18/10092914.aspx)
* [Why does `SHGetSpecialFolderPath` take such a long time before returning a network error?](http://devblogs.com/b/oldnewthing/archive/2011/01/05/10111777.aspx)
* [How do you obtain the icon for a shortcut without the shortcut overlay?](http://devblogs.com/b/oldnewthing/archive/2011/01/27/10120844.aspx) (`SHGetFileInfo()`)
* [Why does `SHGetKnownFolderPath` return `E_FAIL` for a known folder?](http://devblogs.com/b/oldnewthing/archive/2011/02/09/10126508.aspx)
* [How can I get information about the items in the Recycle Bin?](http://devblogs.com/b/oldnewthing/archive/2011/08/30/10202076.aspx)
* [Modernizing our simple program that retrieves information about the items in the Recycle Bin](http://devblogs.com/b/oldnewthing/archive/2011/08/31/10203215.aspx)
* [Invoking commands on items in the Recycle Bin](http://devblogs.com/b/oldnewthing/archive/2011/09/01/10204404.aspx)
* [How do I perform shell file operations while avoiding shell copy hooks?](http://devblogs.com/b/oldnewthing/archive/2012/03/30/10289176.aspx)
* [Command line tool to manage Windows 7 Libraries, with source code](http://devblogs.com/b/oldnewthing/archive/2012/08/28/10343980.aspx) (`IShellLibrary`)
* [`IShellFolder::BindToObject` is a high-traffic method; don't do any heavy lifting](http://devblogs.com/b/oldnewthing/archive/2012/09/14/10349265.aspx)
* [Obtaining the parsing name (and pidl) for a random shell object](http://devblogs.com/b/oldnewthing/archive/2013/02/04/10390725.aspx)
* [Creating a simple pidl: For the times you care enough to send the very fake](http://devblogs.com/b/oldnewthing/archive/2013/05/03/10415778.aspx)
* [Creating a simple shell item, just as fake as a simple pidl](http://devblogs.com/b/oldnewthing/archive/2014/05/19/10526584.aspx)
* [Displaying a property sheet for multiple files](http://devblogs.com/b/oldnewthing/archive/2013/06/17/10426275.aspx)
* [How do I get a high resolution icon for a file?](http://devblogs.com/b/oldnewthing/archive/2014/01/20/10490951.aspx)
* [How do I extract an icon at a nonstandard size if `IExtractIcon::Extract` tells me to go jump in a lake?](http://devblogs.com/b/oldnewthing/archive/2014/05/01/10521770.aspx)
* [How do I read the "Double-click to open an item (single-click to select)" setting in Folder Options?](http://devblogs.com/b/oldnewthing/archive/2014/08/25/10552503.aspx)
* [The wonderful world of shell bind context strings](http://devblogs.com/b/oldnewthing/archive/2015/01/22/10587918.aspx)
* [Helper functions to make shell bind contexts slightly more manageable](http://devblogs.com/b/oldnewthing/archive/2015/01/23/10588226.aspx)
* [Customizing item enumeration with `IShellItem`](http://devblogs.com/b/oldnewthing/archive/2015/01/26/10588645.aspx)
* [Customizing item enumeration with `IShellItem`, the old-fashioned way](http://devblogs.com/b/oldnewthing/archive/2015/02/02/10590344.aspx)
* [How do I create an `IShellItemArray` from a bunch of file paths?](http://devblogs.com/b/oldnewthing/archive/2014/03/14/10507794.aspx)
* [How do I invoke a verb on an `IShellItemArray`?](http://devblogs.com/b/oldnewthing/archive/2012/09/20/10351107.aspx)
* [How does a shell namespace extension provide icons for virtual items that track the standard icons set by the user's file associations?](http://devblogs.com/b/oldnewthing/archive/2015/10/09/10646703.aspx)
* [How do I get the user-customed name of My Computer or Recycle Bin?](http://devblogs.com/b/oldnewthing/archive/2015/10/12/10647157.aspx)
* [How do I get the user-customized name of a mapped network drive?](http://devblogs.com/b/oldnewthing/archive/2015/10/19/10648612.aspx)
* [Enumerating all the programs that can open a particular file extension](https://devblogs.microsoft.com/oldnewthing/20151130-00/?p=92191)
* [Enumerating all the programs that can launch a particular protocol](https://devblogs.microsoft.com/oldnewthing/20151207-00/?p=92341)
* [How do I register a command on the desktop background context menu? (And how do I remove one I don’t like?)](https://devblogs.microsoft.com/oldnewthing/20151208-00/?p=92342)
* [How can I get the canonical name for a known folder?](https://devblogs.microsoft.com/oldnewthing/20160208-00/?p=93001)
* [Peeking inside an `IShellItem` to see what it’s made of](https://devblogs.microsoft.com/oldnewthing/20160620-00/?p=93705)
* [Why does `SHGetKnownFolderPath` fail when impersonating?](https://devblogs.microsoft.com/oldnewthing/20160601-00/?p=93555)
* [How do I programmatically add a folder to my Documents library?](https://devblogs.microsoft.com/oldnewthing/20161107-00/?p=94655)
* [Why doesn’t `SHGetFileInfo` give me customized folder icons?](https://devblogs.microsoft.com/oldnewthing/20170501-00/?p=96075)
* [How can I detect that a shell item refers to a virtual folder, or to a file system inside a file?](https://devblogs.microsoft.com/oldnewthing/20171101-00/?p=97325)
* [Why is there a limit of 15 shell icon overlays?](https://devblogs.microsoft.com/oldnewthing/20190313-00/?p=101094)

### Uncategorized COM Stuff
* [The macros for declaring and implementing COM interfaces](http://devblogs.com/b/oldnewthing/archive/2004/10/05/238050.aspx)
* [An introduction to COM connection points](http://devblogs.com/b/oldnewthing/archive/2013/06/11/10424940.aspx)
* [Dispatch interfaces as connection point interfaces](http://devblogs.com/b/oldnewthing/archive/2013/06/12/10425215.aspx)
* [Adjustor thunks](http://devblogs.com/b/oldnewthing/archive/2004/02/06/68695.aspx)
* [What is the underlying object behind a COM interface pointer?](http://devblogs.com/b/oldnewthing/archive/2007/04/24/2252261.aspx)
* [How to turn off the exception handler that COM "helpfully" wraps around your server](http://devblogs.com/b/oldnewthing/archive/2011/01/20/10117963.aspx)
* [Shortcuts are serializable objects, which means that they can be stored in places other than just a file](http://devblogs.com/b/oldnewthing/archive/2011/02/24/10133280.aspx)
* [Why does` IFileOperation` skip junctions even though I passed `FOFX_NOSKIPJUNCTIONS`?](http://devblogs.com/b/oldnewthing/archive/2011/08/18/10197030.aspx)
* [Nasty gotcha: `STGM_READ | STGM_WRITE` does not grant read/write access](http://devblogs.com/b/oldnewthing/archive/2013/07/19/10435335.aspx)
* [How can I get the list of programs the same way that Programs and Features gets it?](http://devblogs.com/b/oldnewthing/archive/2013/12/30/10485905.aspx)
* [How do I obtain the computer manufacturer's name via C++?](http://devblogs.com/b/oldnewthing/archive/2014/01/06/10487119.aspx) (`IWbemClassObject`)
* [The stream pointer position in `IDataObject::GetData` and `IDataObject::GetDataHere` is significant](http://devblogs.com/b/oldnewthing/archive/2014/09/18/10558763.aspx)
* [The sad implementation history of COM component categories and why it means you have to click twice to see your newly-installed taskbar toolbar](https://devblogs.microsoft.com/oldnewthing/20171121-00/?p=97435)
* [How do I request that my out-of-process COM server run unelevated?](https://devblogs.microsoft.com/oldnewthing/20180905-00/?p=99655)
* [How can a desktop app use a Windows Runtime object that infers UI context from its thread? The `IInitializeWithWindow` pattern](https://devblogs.microsoft.com/oldnewthing/20190412-00/?p=102413) (`IInitialize­With­Window`)

## Memory

* [Stupid memory-mapping tricks](https://devblogs.microsoft.com/oldnewthing/20031007-00/?p=42263)
* [Creating a shared memory block that can grow in size](https://devblogs.microsoft.com/oldnewthing/20150130-00/?p=44793)
* [Why do I have to pass a valid page protection value to `VirtualAlloc` even if it ignores it?](https://devblogs.microsoft.com/oldnewthing/20171227-00/?p=97656)
* [How can I include/exclude specific memory blocks in user-mode crash dumps?](https://devblogs.microsoft.com/oldnewthing/20181011-00/?p=99945)

## Input and Output
* [Developing the method for taking advantage of the fact that the `OVERLAPPED` associated with asynchronous I/O is passed by address](http://devblogs.com/b/oldnewthing/archive/2010/12/20/10107027.aspx)
* [What's the difference between an asynchronous `PIPE_WAIT` pipe and a `PIPE_NOWAIT` pipe?](http://devblogs.com/b/oldnewthing/archive/2011/01/14/10115610.aspx)
* [Ready... cancel... wait for it! (part 1)](http://devblogs.com/b/oldnewthing/archive/2011/02/02/10123392.aspx)
* [Ready... cancel... wait for it! (part 2)](http://devblogs.com/b/oldnewthing/archive/2011/02/03/10124060.aspx)
* [Ready... cancel... wait for it! (part 3)](http://devblogs.com/b/oldnewthing/archive/2011/02/04/10124610.aspx)
* [If you're waiting for I/O to complete, it helps if you actually have an I/O to begin with](http://devblogs.com/b/oldnewthing/archive/2011/03/03/10136241.aspx)
* [Be careful when redirecting both a process's `stdin` and `stdout` to pipes, for you can easily deadlock](http://devblogs.com/b/oldnewthing/archive/2011/07/07/10183884.aspx)
* [Looking at the problem at the wrong level: Closing a process's `stdin`](http://devblogs.com/b/oldnewthing/archive/2011/07/06/10183368.aspx)
* [`ReadDirectoryChangesW` reads directory changes, but what if the directory doesn't change?](http://devblogs.com/b/oldnewthing/archive/2011/08/12/10195186.aspx)
* [Why does my asynchronous I/O complete synchronously?](http://devblogs.com/b/oldnewthing/archive/2011/09/23/10215586.aspx)
* [How do `FILE_FLAG_SEQUENTIAL_SCAN` and `FILE_FLAG_RANDOM_ACCESS` affect how the operating system treats my file?](http://devblogs.com/b/oldnewthing/archive/2012/01/20/10258690.aspx)
* [You can use an `OVERLAPPED` structure with synchronous I/O, too](http://devblogs.com/b/oldnewthing/archive/2012/04/05/10290954.aspx)
* [If an asynchronous I/O completes synchronously, is the `hEvent` in the `OVERLAPPED` structure signaled anyway?](http://devblogs.com/b/oldnewthing/archive/2014/02/06/10497096.aspx)
* [We're currently using `FILE_FLAG_NO_BUFFERING` and `FILE_FLAG_WRITE_THROUGH`, but we would like our `WriteFile` to go even faster](http://devblogs.com/b/oldnewthing/archive/2014/03/06/10505524.aspx)
* [Why does my synchronous overlapped `ReadFile` return `FALSE` when the end of the file is reached?](http://devblogs.com/b/oldnewthing/archive/2015/01/21/10587660.aspx)
* [`CancelIoEx` can cancel I/O on console input, which is kind of nice](http://devblogs.com/b/oldnewthing/archive/2015/03/23/10601947.aspx)
* [If I issue a second overlapped I/O operation without waiting for the first one to complete, are they still guaranteed to complete in order?](https://devblogs.microsoft.com/oldnewthing/20160205-00/?p=92981)
* [Why does `SetFileValidData` fail even though I enabled the `SE_MANAGE_VOLUME_NAME` privilege?](https://devblogs.microsoft.com/oldnewthing/20160603-00/?p=93565)
* [Is `GENERIC_ALL` equivalent to `GENERIC_READ | GENERIC_WRITE | GENERIC_EXECUTE`?](https://devblogs.microsoft.com/oldnewthing/20170310-00/?p=95705)
* [`CancelIoEx` can cancel synchronous I/O, which is kind of nice](https://devblogs.microsoft.com/oldnewthing/20170928-00/?p=97105)
* [Why does `IsPathRelative` return `FALSE` for paths that are drive-relative?](https://devblogs.microsoft.com/oldnewthing/20180222-00/?p=98075)
* [Why are my file write operations synchronous, even though I opened the file as `FILE_FLAG_OVERLAPPED`?](https://devblogs.microsoft.com/oldnewthing/20180725-00/?p=99335)
* [File-extending writes are not always synchronous, which is entirely within the contract](https://devblogs.microsoft.com/oldnewthing/20181019-00/?p=100015)

### Files and Directories
* [The Definitive Guide on Win32 to NT Path Conversion](http://googleprojectzero.blogspot.cz/2016/02/the-definitive-guide-on-win32-to-nt.html)
* [How can I tell that a directory is really a recycle bin?](http://devblogs.com/b/oldnewthing/archive/2008/09/18/8956382.aspx)
* [How can I tell that a directory is weird and should be excluded from the user interface?](http://devblogs.com/b/oldnewthing/archive/2008/09/19/8957958.aspx)
* [How do I get information about the target of a symbolic link?](http://devblogs.com/b/oldnewthing/archive/2010/02/12/9962359.aspx)
* [How do I access a file without updating its last-access time?](http://devblogs.com/b/oldnewthing/archive/2011/10/10/10222560.aspx)
* [How do I show the contents of a directory while respecting the user's preferences for hidden and super-hidden files as well as the user's language preferences?](http://devblogs.com/b/oldnewthing/archive/2014/03/17/10508309.aspx)
* [You can use a file as a synchronization object, too](http://devblogs.com/b/oldnewthing/archive/2014/09/05/10555220.aspx)
* [How can I append to a file and know where it got written, even if the file is being updated by multiple processes?](https://devblogs.microsoft.com/oldnewthing/20151127-00/?p=92211)
* [The `FILE_FLAG_DELETE_ON_CLOSE` flag applies to the handle, also known as the file object, which is not the same as the file](https://devblogs.microsoft.com/oldnewthing/20160108-00/?p=92821)
* [How long do I have to keep the `SECURITY_ATTRIBUTES` and `SECURITY_DESCRIPTOR` structures valid after using them to create a file?](https://devblogs.microsoft.com/oldnewthing/20160520-00/?p=93497)
* [How do I create a directory where people can create subdirectories but cannot mess with those created by other users?](https://devblogs.microsoft.com/oldnewthing/20160524-00/?p=93515)
* [How can I tell whether a file is on a removable drive, a fixed drive, or a remote drive?](https://devblogs.microsoft.com/oldnewthing/20160602-00/?p=93556)
* [Why does a non-recursive `Read­Directory­ChangesW` still report files created inside subdirectories?](https://devblogs.microsoft.com/oldnewthing/20180712-00/?p=99225)
* [The early history of Windows file attributes, and why there is a gap between System and Directory](https://devblogs.microsoft.com/oldnewthing/20180830-00/?p=99615)
* [Even if you open a file with GUID, you can still get its name, or at least one of its names](https://devblogs.microsoft.com/oldnewthing/20190410-00/?p=102408) (`GetFinalPathNameByHandle()`)

### ACL
* [The `MoveSecurityAttributes` policy affects only how Explorer recalculates ACLs when a file is moved; everybody else is on their own](http://devblogs.com/b/oldnewthing/archive/2015/10/14/10647632.aspx)
* [How to create a folder that inherits its parent’s ACL, and then overrides part of it](https://devblogs.microsoft.com/oldnewthing/20170223-00/?p=95545)

## Security Permissions, Attributes and Identifiers

* [What is the default security descriptor?](http://devblogs.com/b/oldnewthing/archive/2004/03/12/88572.aspx)
* [How do I convert a SID between binary and string forms?](http://devblogs.com/b/oldnewthing/archive/2004/03/15/89753.aspx)
* [An easy way to determine whether you have a particular file permission](http://devblogs.com/b/oldnewthing/archive/2004/06/04/148426.aspx)
* [What are the access rights and privileges that control changing ownership of an object?](http://devblogs.com/b/oldnewthing/archive/2005/08/18/453054.aspx)
* [How do the names in the file security dialog map to access control masks?](http://devblogs.com/b/oldnewthing/archive/2007/07/26/4052149.aspx)
* [If you ask for `STANDARD_RIGHTS_REQUIRED`, you may as well ask for the moon](http://devblogs.com/b/oldnewthing/archive/2008/02/27/7912126.aspx)
* [A user's SID can change, so make sure to check the SID history](http://devblogs.com/b/oldnewthing/archive/2014/11/28/10576639.aspx)
* [Detecting whether a SID is well-known SID](http://devblogs.com/b/oldnewthing/archive/2014/12/12/10580256.aspx)
* [What's the point of giving my unnamed object proper security attributes since unnamed objects aren't accessible outside the process anyway (or are they?)](http://devblogs.com/b/oldnewthing/archive/2015/06/04/10619379.aspx)
* [Is a SID with zero subauthorities a valid SID? It depends whom you ask](http://devblogs.com/b/oldnewthing/archive/2015/07/02/10624288.aspx)
* [What’s the difference between duplicating the handle to a token and duplicating a token?](https://devblogs.microsoft.com/oldnewthing/20160511-00/?p=93446)
* [I called `AdjustTokenPrivileges`, but I was still told that a necessary privilege was not held](https://devblogs.microsoft.com/oldnewthing/20190531-00/?p=102532)

## Registry

* [Beware of non-null-terminated registry strings](https://devblogs.microsoft.com/oldnewthing/20040824-00/?p=38063)
* [The performance cost of reading a registry key](https://devblogs.microsoft.com/oldnewthing/20060222-11/?p=32193)
* [So how bad is it that I’m calling `RegOpenKey` instead of `RegOpenKeyEx`?](https://devblogs.microsoft.com/oldnewthing/20160120-00/?p=92892)
* [If I simply want to create a registry key but don’t intend to do anything else with it, what security access mask should I ask for?](https://devblogs.microsoft.com/oldnewthing/20161128-00/?p=94815)
* [How can I programmatically inspect and manipulate a registry hive file without mounting it?](https://devblogs.microsoft.com/oldnewthing/20181015-00/?p=99975)
* [Why doesn’t `RegSetKeySecurity` propagate inheritable ACEs, but `SetSecurityInfo` does?](https://devblogs.microsoft.com/oldnewthing/20200102-00/?p=103287)

## Locale

* [Nasty gotcha: `SetThreadUILanguage` cannot be used to restore the thread UI language](https://devblogs.microsoft.com/oldnewthing/20170908-00/?p=96965)

## NT Services

* [Calling `ShutdownBlockReasonCreate` from my service doesn't stop the user from shutting down](https://devblogs.microsoft.com/oldnewthing/20151002-00/?p=91461)
* [What does it mean when my attempt to stop a Windows NT service fails with `ERROR_BROKEN_PIPE`?](https://devblogs.microsoft.com/oldnewthing/20190405-00/?p=102389)

## Uncategorized

* [How do I determine the processor's cache line size?](http://devblogs.com/b/oldnewthing/archive/2009/12/08/9933836.aspx) (`GetLogicalProcessorInformation()`)
* [Why are structure sizes checked strictly?](http://devblogs.com/b/oldnewthing/archive/2003/12/12/56061.aspx)
* [What's the difference between `CreateMenu` and `CreatePopupMenu`?](http://devblogs.com/b/oldnewthing/archive/2003/12/30/46594.aspx)
* [`TEXT` vs. `_TEXT` vs. `_T`, and `UNICODE` vs. `_UNICODE`](http://devblogs.com/b/oldnewthing/archive/2004/02/12/71851.aspx)
* [Why are `HANDLE` return values so inconsistent?](http://devblogs.com/b/oldnewthing/archive/2004/03/02/82639.aspx)
* [How to retrieve text under the cursor (mouse pointer)](http://devblogs.com/b/oldnewthing/archive/2004/04/23/118893.aspx)
* [How to detect programmatically whether you are running on 64-bit Windows](http://devblogs.com/b/oldnewthing/archive/2005/02/01/364563.aspx)
* [A timed context menu](http://devblogs.com/b/oldnewthing/archive/2005/03/07/387044.aspx)
* [The importance of passing the `WT_EXECUTELONGFUNCTION` flag to `QueueUserWorkItem`](http://devblogs.com/b/oldnewthing/archive/2005/07/22/441785.aspx)
* [If your callback fails, it's your responsibility to set the error code](http://devblogs.com/b/oldnewthing/archive/2006/01/23/516202.aspx)
* [The double-click time tells the window manager how good your reflexes are](http://devblogs.com/b/oldnewthing/archive/2008/04/23/8417521.aspx)
* [The cursor isn't associated with a window or a window class; it's associated with a thread group](http://devblogs.com/b/oldnewthing/archive/2011/02/07/10125509.aspx)
* [Menu item states are not reliable until they are shown because they aren't needed until then](http://devblogs.com/b/oldnewthing/archive/2011/08/05/10192952.aspx)
* [How can I display a live screenshot of a piece of another application?](http://devblogs.com/b/oldnewthing/archive/2013/05/13/10417964.aspx)
* [Converting from a UTC-based `SYSTEMTIME` directly to a local-time-based `SYSTEMTIME`](http://devblogs.com/b/oldnewthing/archive/2014/03/07/10505926.aspx)
* [Programmatically uploading a file to an FTP site](http://devblogs.com/b/oldnewthing/archive/2014/03/10/10506422.aspx)
* [How can you use both versions 5 and 6 of the common controls within the same module?](http://devblogs.com/b/oldnewthing/archive/2014/05/08/10523522.aspx)
* [How can I tell if Windows Update is waiting for the system to reboot?](http://devblogs.com/b/oldnewthing/archive/2015/09/21/10642727.aspx)
* [How do I call `SetTimer` with a timer ID that is guaranteed not to conflict with any other timer ID?](http://devblogs.com/b/oldnewthing/archive/2015/09/24/10643494.aspx)
* [A window can’t have two timers with the same ID, so how do I assign an ID that nobody else is using?](https://devblogs.microsoft.com/oldnewthing/20191009-00/?p=102974)
* [What does it mean when a display change is temporary?](http://devblogs.com/b/oldnewthing/archive/2008/01/04/6973747.aspx)
* [How do I obtain the comment for a share?](http://devblogs.com/b/oldnewthing/archive/2015/10/05/10645685.aspx)
* [How accurate are the various Windows time-querying functions?](https://devblogs.microsoft.com/oldnewthing/20170921-00/?p=97057)
* [How can I detect whether the user is logging off?](https://devblogs.microsoft.com/oldnewthing/20180705-00/?p=99175)
* [The sad history of Unicode `printf`-style format specifiers in Visual C++](https://devblogs.microsoft.com/oldnewthing/20190830-00/?p=102823)
* [Why are timer IDs and dialog control IDs 64-bit values on 64-bit Windows? Did you really expect people to create more than 4 billion timers or dialog controls?](https://devblogs.microsoft.com/oldnewthing/20191010-00/?p=102978)
* [If you suppress GDI+ background thread, then you are expected to pump messages yourself](https://devblogs.microsoft.com/oldnewthing/20191029-00/?p=103033)
