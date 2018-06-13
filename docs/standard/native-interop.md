---
title: Interoperabilità nativa
description: Informazioni su come interagire con i componenti nativi in .NET.
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
ms.openlocfilehash: 7da86cfe483a2355c53206f4c491fbd07e4c3046
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591924"
---
# <a name="native-interoperability"></a><span data-ttu-id="fe9d1-103">Interoperabilità nativa</span><span class="sxs-lookup"><span data-stu-id="fe9d1-103">Native Interoperability</span></span>

<span data-ttu-id="fe9d1-104">In questo documento vengono descritti in modo approfondito i tre modi di ottenere l'"interoperabilità nativa" disponibili in .NET.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-104">In this document, we will dive a little bit deeper into all three ways of doing "native interoperability" that are available using .NET.</span></span>

<span data-ttu-id="fe9d1-105">Esistono alcuni motivi che rendono necessaria la chiamata del codice nativo:</span><span class="sxs-lookup"><span data-stu-id="fe9d1-105">There are a few of reasons why you would want to call into native code:</span></span>

*   <span data-ttu-id="fe9d1-106">Sistemi operativi dotati di un volume elevato di API che non sono presenti nelle librerie di classi gestite.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-106">Operating Systems come with a large volume of APIs that are not present in the managed class libraries.</span></span> <span data-ttu-id="fe9d1-107">Un ottimo esempio è l'accesso alle funzioni di gestione dell'hardware o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-107">A prime example for this would be access to hardware or operating system management functions.</span></span>
*   <span data-ttu-id="fe9d1-108">Comunicazione con altri componenti che hanno o possono generare ABI di tipo C (ABI native).</span><span class="sxs-lookup"><span data-stu-id="fe9d1-108">Communicating with other components that have or can produce C-style ABIs (native ABIs).</span></span> <span data-ttu-id="fe9d1-109">Questo può riguardare, ad esempio, codice Java esposto tramite [JNI (Java Native Interface)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) o qualsiasi altro linguaggio gestito in grado di generare un componente nativo.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-109">This covers, for example, Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
*   <span data-ttu-id="fe9d1-110">In Windows la maggior parte del software installato, ad esempio la suite Microsoft Office, registra i componenti COM che rappresentano i propri programmi e consente agli sviluppatori di automatizzarli o di usarli.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-110">On Windows, most of the software that gets installed, such as Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="fe9d1-111">Anche questo richiede interoperabilità nativa.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-111">This also requires native interoperability.</span></span>

<span data-ttu-id="fe9d1-112">L'elenco sopra riportato, naturalmente, non esaurisce tutti i potenziali scenari e situazioni in cui lo sviluppatore vuole, preferisce o ha bisogno di interfacciarsi con i componenti nativi.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-112">Of course, the list above does not cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="fe9d1-113">La libreria di classi .NET, ad esempio, usa il supporto per l'interoperabilità nativa per implementare un numero notevole di API, ad esempio il supporto e la manipolazione della console, l'accesso al file system e altro.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-113">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="fe9d1-114">È tuttavia importante notare che, qualora fosse necessaria, questa opzione è comunque disponibile.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-114">However, it is important to note that there is an option, should one need it.</span></span>

> [!NOTE]
> <span data-ttu-id="fe9d1-115">La maggior parte degli esempi riportati in questo documento viene presentata per tutte e tre le piattaforme supportate in .NET Core (Windows, Linux e macOS).</span><span class="sxs-lookup"><span data-stu-id="fe9d1-115">Most of the examples in this document will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="fe9d1-116">Per alcuni esempi brevi e illustrativi, tuttavia, verrà presentata solo la versione che usa nomi file ed estensioni Windows, come "dll" per le librerie.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-116">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="fe9d1-117">Questo non significa che le funzionalità illustrate non siano disponibili in Linux o macOS. La scelta dipende infatti solo da motivi di praticità.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-117">This does not mean that those features are not available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="platform-invoke-pinvoke"></a><span data-ttu-id="fe9d1-118">Platform Invoke (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="fe9d1-118">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="fe9d1-119">P/Invoke è una tecnologia che consente di accedere dal codice gestito a strutture, callback e funzioni presenti in librerie non gestite.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-119">P/Invoke is a technology that allows you to access structs, callbacks and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="fe9d1-120">La maggior parte delle API di P/Invoke è contenuta in due spazi dei nomi: `System` e `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-120">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="fe9d1-121">Usando questi due spazi dei nomi è possibile accedere agli attributi che descrivono il modo in cui si vuole comunicare con il componente nativo.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-121">Using these two namespaces will allow you access to the attributes that describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="fe9d1-122">Per iniziare viene mostrato l'esempio più comune, ovvero la chiamata di funzioni non gestite nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-122">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="fe9d1-123">Di seguito viene visualizzata una finestra di messaggio da un'applicazione della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="fe9d1-123">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="fe9d1-124">L'esempio precedente è piuttosto semplice, ma mostra chiaramente gli elementi necessari per richiamare funzioni non gestite da un codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-124">The example above is pretty simple, but it does show off what is needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="fe9d1-125">Di seguito l'esempio viene descritto in modo dettagliato:</span><span class="sxs-lookup"><span data-stu-id="fe9d1-125">Let’s step through the example:</span></span>

*   <span data-ttu-id="fe9d1-126">La riga 1 mostra l'uso dell'istruzione per `System.Runtime.InteropServices`, ovvero lo spazio dei nomi contenente tutti gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-126">Line #1 shows the using statement for the `System.Runtime.InteropServices` which is the namespace that holds all of the items we need.</span></span>
*   <span data-ttu-id="fe9d1-127">La riga 5 introduce l'attributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-127">Line #5 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="fe9d1-128">Questo attributo è fondamentale, in quanto comunica al runtime che deve caricare la DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-128">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="fe9d1-129">Si tratta della DLL di cui si vuole richiamare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-129">This is the DLL into which we wish to invoke.</span></span>
*   <span data-ttu-id="fe9d1-130">La riga 6 è il punto cruciale dell'attività di P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-130">Line #6 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="fe9d1-131">Definisce un metodo gestito che ha **esattamente la stessa firma** del metodo non gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-131">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="fe9d1-132">Come è possibile notare, la dichiarazione dispone di una nuova parola chiave, `extern`, che indica al runtime che si tratta di un metodo esterno. Quando si richiama tale metodo, il runtime dovrebbe individuarlo nella DLL specificata nell'attributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-132">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="fe9d1-133">La restante parte dell'esempio è semplicemente la chiamata del metodo, analoga alla chiamata di qualsiasi altro metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-133">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="fe9d1-134">L'esempio è simile per macOS.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-134">The sample is similar for macOS.</span></span> <span data-ttu-id="fe9d1-135">Uno degli elementi che è necessario cambiare è, naturalmente, il nome della libreria nell'attributo `DllImport`, poiché macOS utilizza un differente schema di denominazione delle librerie dinamiche.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-135">One thing that needs to change is, of course, the name of the library in the `DllImport` attribute, as macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="fe9d1-136">Nell'esempio seguente viene usata la funzione `getpid(2)` per ottenere l'ID processo dell'applicazione e stamparlo nella console.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-136">The sample below uses the `getpid(2)` function to get the process ID of the application and print it out to the console.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="fe9d1-137">È simile anche in Linux.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-137">It is also similar on Linux.</span></span> <span data-ttu-id="fe9d1-138">Il nome della funzione è lo stesso, dal momento che `getpid(2)` è una chiamata di sistema [POSIX](https://en.wikipedia.org/wiki/POSIX) standard.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-138">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

### <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="fe9d1-139">Richiamare codice gestito da codice non gestito</span><span class="sxs-lookup"><span data-stu-id="fe9d1-139">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="fe9d1-140">Il runtime consente naturalmente la comunicazione in entrambe le direzioni, permettendo di chiamare elementi gestiti da funzioni native usando puntatori alle funzioni.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-140">Of course, the runtime allows communication to flow both ways which enables you to call into managed artifacts from native functions, using function pointers.</span></span> <span data-ttu-id="fe9d1-141">In un codice gestito l'elemento più simile a un puntatore a funzione è un **delegato**. Viene quindi usato un delegato per consentire i callback dal codice nativo al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-141">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="fe9d1-142">La modalità di uso di questa funzionalità è simile al processo di passaggio dal codice gestito a quello nativo descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-142">The way to use this feature is similar to managed to native process described above.</span></span> <span data-ttu-id="fe9d1-143">Per un determinato callback, viene definito un delegato corrispondente alla firma. Tale delegato viene quindi passato al metodo esterno.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-143">For a given callback, you define a delegate that matches the signature, and pass that into the external method.</span></span> <span data-ttu-id="fe9d1-144">Il runtime eseguirà tutte le altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-144">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="fe9d1-145">Prima di analizzare l'esempio, è opportuno esaminare le firme delle funzioni non gestite che è necessario utilizzare.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-145">Before we walk through our example, it is good to go over the signatures of the unmanaged functions we need to work with.</span></span> <span data-ttu-id="fe9d1-146">La firma della funzione da chiamare per enumerare tutte le finestre è la seguente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="fe9d1-146">The function we want to call to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="fe9d1-147">Il primo parametro è un callback.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-147">The first parameter is a callback.</span></span> <span data-ttu-id="fe9d1-148">La firma di tale callback è la seguente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="fe9d1-148">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="fe9d1-149">Tenendo presente questo, passare ad analizzare l'esempio:</span><span class="sxs-lookup"><span data-stu-id="fe9d1-149">With this in mind, let’s walk through the example:</span></span>

*   <span data-ttu-id="fe9d1-150">La riga 8 dell'esempio definisce un delegato che corrisponde alla firma del callback da un codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-150">Line #8 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="fe9d1-151">Si noti che i tipi LPARAM e HWND vengono rappresentati usando `IntPtr` nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-151">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="fe9d1-152">Le righe 10 e 11 introducono la funzione `EnumWindows` dalla libreria user32.dll.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-152">Lines #10 and #11 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="fe9d1-153">Le righe da 13 a 16 implementano il delegato.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-153">Lines #13 - 16 implement the delegate.</span></span> <span data-ttu-id="fe9d1-154">Per questo semplice esempio si vuole eseguire l'output dell'handle alla console.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-154">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="fe9d1-155">Nella riga 19, infine, il metodo esterno viene richiamato e passato al delegato.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-155">Finally, in line #19 we invoke the external method and pass in the delegate.</span></span>

<span data-ttu-id="fe9d1-156">Gli esempi Linux e macOS sono riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-156">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="fe9d1-157">Per questi esempi viene usata la funzione `ftw` disponibile in `libc`, la libreria C.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-157">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="fe9d1-158">Questa funzione viene usata per scorrere le gerarchie di directory e accetta un puntatore a una funzione come uno dei propri parametri.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-158">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="fe9d1-159">Tale funzione ha la firma seguente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-159">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="fe9d1-160">Nell'esempio macOS viene usata la stessa funzione. L'unica differenza è l'argomento dell'attributo `DllImport`, dal momento che macOS mantiene `libc` in una posizione differente.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-160">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code. You can find more information
        // about this in the section on marshalling below.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="fe9d1-161">Entrambi gli esempi precedenti dipendono da parametri e in entrambi i casi i parametri vengono forniti come tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-161">Both of the above examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="fe9d1-162">Il runtime esegue le operazioni necessarie ed elabora i parametri ottenendo i relativi equivalenti sull'altro lato.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-162">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="fe9d1-163">Poiché questo processo è molto importante per la scrittura di codice di interoperabilità nativa di qualità, è opportuno sapere cosa succede quando il runtime _effettua il marshalling_ dei tipi.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-163">Since this process is really important to writing quality native interop code, let’s take a look at what happens when the runtime _marshals_ the types.</span></span>

## <a name="type-marshalling"></a><span data-ttu-id="fe9d1-164">Marshalling dei tipi</span><span class="sxs-lookup"><span data-stu-id="fe9d1-164">Type marshalling</span></span>

<span data-ttu-id="fe9d1-165">Il termine **marshalling** indica il processo di trasformazione dei tipi quando questi devono passare dal codice gestito a quello nativo e viceversa.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-165">**Marshalling** is the process of transforming types when they need to cross the managed boundary into native and vice versa.</span></span>

<span data-ttu-id="fe9d1-166">Il motivo per cui il marshalling è necessario è che i tipi presenti nel codice gestito e quelli presenti nel codice non gestito sono differenti.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-166">The reason marshalling is needed is because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="fe9d1-167">Nel codice gestito, ad esempio, si ha un elemento `String`, mentre nell'ambiente non gestito le stringhe possono essere Unicode ("wide"), non Unicode, con terminazione null, ASCII, e così via. Per impostazione predefinita, il sottosistema di P/Invoke tenterà di eseguire le operazioni necessarie in base al comportamento predefinito descritto in [MSDN](../../docs/framework/interop/default-marshaling-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="fe9d1-167">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem will try to do the Right Thing based on the default behavior which you can see on [MSDN](../../docs/framework/interop/default-marshaling-behavior.md).</span></span> <span data-ttu-id="fe9d1-168">Tuttavia, per i casi in cui è necessario un controllo aggiuntivo, è possibile usare l'attributo `MarshalAs` per specificare il tipo previsto sul lato non gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-168">However, for those situations where you need extra control, you can employ the `MarshalAs` attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="fe9d1-169">Ad esempio, se si vuole che la stringa venga inviata come stringa ANSI con terminazione null, è possibile usare un codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fe9d1-169">For instance, if we want the string to be sent as a null-terminated ANSI string, we could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

### <a name="marshalling-classes-and-structs"></a><span data-ttu-id="fe9d1-170">Marshalling di classi e strutture</span><span class="sxs-lookup"><span data-stu-id="fe9d1-170">Marshalling classes and structs</span></span>

<span data-ttu-id="fe9d1-171">Un altro aspetto del marshalling dei tipi è il modo in cui è possibile passare una struttura a un metodo non gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-171">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="fe9d1-172">Ad esempio, alcuni dei metodi non gestiti richiedono una struttura come parametro.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-172">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="fe9d1-173">In questi casi, è necessario creare una classe o una struttura corrispondente nel codice gestito per usarla come parametro.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-173">In these cases, we need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="fe9d1-174">La semplice definizione della classe, tuttavia, non è sufficiente. È necessario anche indicare al gestore di marshalling come eseguire il mapping dei campi della classe alla struttura non gestita.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-174">However, just defining the class is not enough, we also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="fe9d1-175">A questo punto entra in gioco l'attributo `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-175">This is where the `StructLayout` attribute comes into play.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="fe9d1-176">L'esempio precedente mostra una semplice chiamata alla funzione `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-176">The example above shows off a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="fe9d1-177">La parte interessante è alla riga 4.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-177">The interesting bit is on line 4.</span></span> <span data-ttu-id="fe9d1-178">L'attributo specifica che i campi della classe devono essere mappati in modo sequenziale allo struct sull'altro lato (non gestito).</span><span class="sxs-lookup"><span data-stu-id="fe9d1-178">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="fe9d1-179">Questo significa che i nomi dei campi non sono rilevanti, ma che è importante solo l'ordine. È infatti necessario che i campi corrispondano alla struttura non gestita, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fe9d1-179">This means that the naming of the fields is not important, only their order is important, as it needs to correspond to the unmanaged struct, shown below:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="fe9d1-180">La procedura per Linux e macOS è già stata mostrata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-180">We already saw the Linux and macOS example for this in the previous example.</span></span> <span data-ttu-id="fe9d1-181">Viene comunque mostrata anche di seguito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-181">It is shown again below.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public class StatClass {
        public uint DeviceID;
        public uint InodeNumber;
        public uint Mode;
        public uint HardLinks;
        public uint UserID;
        public uint GroupID;
        public uint SpecialDeviceID;
        public ulong Size;
        public ulong BlockSize;
        public uint Blocks;
        public long TimeLastAccess;
        public long TimeLastModification;
        public long TimeLastStatusChange;
}
```

<span data-ttu-id="fe9d1-182">La classe `StatClass` rappresenta una struttura restituita dalla chiamata di sistema `stat` nei sistemi UNIX.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-182">The `StatClass` class represents a structure that is returned by the `stat` system call on UNIX systems.</span></span> <span data-ttu-id="fe9d1-183">Rappresenta informazioni su un determinato file.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-183">It represents information about a given file.</span></span> <span data-ttu-id="fe9d1-184">La classe precedente è la rappresentazione statica della struttura nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-184">The class above is the stat struct representation in managed code.</span></span> <span data-ttu-id="fe9d1-185">Anche in questo caso, i campi della classe devono essere nello stesso ordine della struttura nativa (per informazioni, consultare le pagine di manuale relative all'implementazione UNIX preferita) e devono essere dello stesso tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-185">Again, the fields in the class have to be in the same order as the native struct (you can find these by perusing man pages on your favorite UNIX implementation) and they have to be of the same underlying type.</span></span>

## <a name="more-resources"></a><span data-ttu-id="fe9d1-186">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="fe9d1-186">More resources</span></span>

*   <span data-ttu-id="fe9d1-187">[PInvoke.net wiki](https://www.pinvoke.net/): accurata pagina wiki con informazioni sulle API Win32 più comuni e sul modo di richiamarle.</span><span class="sxs-lookup"><span data-stu-id="fe9d1-187">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="fe9d1-188">P/Invoke in MSDN</span><span class="sxs-lookup"><span data-stu-id="fe9d1-188">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="fe9d1-189">Documentazione su Mono in P/Invoke</span><span class="sxs-lookup"><span data-stu-id="fe9d1-189">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
