---
title: Platform Invoke (P/Invoke)
description: Informazioni su come chiamare funzioni native tramite P/Invoke in .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 51026eab92ae4fd47ccdd78321be21bdbb5ecf49
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981257"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="7e6a5-103">Platform Invoke (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="7e6a5-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="7e6a5-104">P/Invoke è una tecnologia che consente di accedere dal codice gestito a struct, callback e funzioni presenti in librerie non gestite.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="7e6a5-105">La maggior parte delle API di P/Invoke è contenuta in due spazi dei nomi: `System` e `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="7e6a5-106">Usando questi due spazi dei nomi si ottengono gli strumenti per descrivere il modo in cui si vuole comunicare con il componente nativo.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="7e6a5-107">Per iniziare viene mostrato l'esempio più comune, ovvero la chiamata di funzioni non gestite nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="7e6a5-108">Di seguito viene visualizzata una finestra di messaggio da un'applicazione della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-108">Let’s show a message box from a command-line application:</span></span>

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

<span data-ttu-id="7e6a5-109">L'esempio precedente è semplice, ma mostra chiaramente gli elementi necessari per richiamare funzioni non gestite da codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="7e6a5-110">Di seguito l'esempio viene descritto in modo dettagliato:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="7e6a5-111">La riga 1 mostra l'istruzione using per lo spazio dei nomi `System.Runtime.InteropServices` contenente tutti gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="7e6a5-112">La riga 7 introduce l'attributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="7e6a5-113">Questo attributo è fondamentale, in quanto comunica al runtime che deve caricare la DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="7e6a5-114">La stringa passata è la DLL che contiene la funzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-114">The string passed in is the DLL our target function is in.</span></span>
*   <span data-ttu-id="7e6a5-115">La riga 8 è il punto cruciale dell'attività di P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-115">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="7e6a5-116">Definisce un metodo gestito che ha **esattamente la stessa firma** del metodo non gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-116">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="7e6a5-117">Come è possibile notare, la dichiarazione dispone di una nuova parola chiave, `extern`, che indica al runtime che si tratta di un metodo esterno. Quando si richiama tale metodo, il runtime dovrebbe individuarlo nella DLL specificata nell'attributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-117">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="7e6a5-118">La restante parte dell'esempio è semplicemente la chiamata del metodo, analoga alla chiamata di qualsiasi altro metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-118">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="7e6a5-119">L'esempio è simile per macOS.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-119">The sample is similar for macOS.</span></span> <span data-ttu-id="7e6a5-120">Il nome della libreria nell'attributo `DllImport` deve essere modificato perché macOS usa uno schema diverso di denominazione delle librerie dinamiche.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-120">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="7e6a5-121">L'esempio seguente usa la funzione `getpid(2)` per ottenere l'ID processo dell'applicazione e stamparlo nella console:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-121">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

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

<span data-ttu-id="7e6a5-122">È simile anche in Linux.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-122">It is also similar on Linux.</span></span> <span data-ttu-id="7e6a5-123">Il nome della funzione è lo stesso, dal momento che `getpid(2)` è una chiamata di sistema [POSIX](https://en.wikipedia.org/wiki/POSIX) standard.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-123">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

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

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="7e6a5-124">Richiamare codice gestito da codice non gestito</span><span class="sxs-lookup"><span data-stu-id="7e6a5-124">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="7e6a5-125">Il runtime consente la comunicazione in entrambe le direzioni, permettendo il callback in codice gestito da funzioni native usando puntatori alle funzioni.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-125">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="7e6a5-126">In un codice gestito l'elemento più simile a un puntatore a funzione è un **delegato**. Viene quindi usato un delegato per consentire i callback dal codice nativo al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-126">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="7e6a5-127">La modalità di uso di questa funzionalità è simile al processo di passaggio dal codice gestito a quello nativo descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-127">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="7e6a5-128">Per un determinato callback, viene definito un delegato corrispondente alla firma e tale delegato viene quindi passato al metodo esterno.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-128">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="7e6a5-129">Il runtime eseguirà tutte le altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-129">The runtime will take care of everything else.</span></span>

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

<span data-ttu-id="7e6a5-130">Prima di analizzare l'esempio, è opportuno esaminare le firme delle funzioni non gestite che è necessario utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-130">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="7e6a5-131">La firma della funzione da chiamare per enumerare tutte le finestre è la seguente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="7e6a5-131">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="7e6a5-132">Il primo parametro è un callback.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-132">The first parameter is a callback.</span></span> <span data-ttu-id="7e6a5-133">La firma di tale callback è la seguente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="7e6a5-133">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="7e6a5-134">A questo punto, è possibile esaminare l'esempio:</span><span class="sxs-lookup"><span data-stu-id="7e6a5-134">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="7e6a5-135">La riga 9 nell'esempio definisce un delegato che corrisponde alla firma del callback da codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-135">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="7e6a5-136">Si noti che i tipi LPARAM e HWND vengono rappresentati usando `IntPtr` nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-136">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="7e6a5-137">Le righe 13 e 14 introducono la funzione `EnumWindows` dalla libreria user32.dll.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-137">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="7e6a5-138">Le righe da 17 a 20 implementano il delegato.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-138">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="7e6a5-139">Per questo semplice esempio si vuole eseguire l'output dell'handle alla console.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-139">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="7e6a5-140">Nella riga 24, infine, il metodo esterno viene chiamato e passato al delegato.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-140">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="7e6a5-141">Gli esempi Linux e macOS sono riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-141">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="7e6a5-142">Per questi esempi viene usata la funzione `ftw` disponibile in `libc`, la libreria C.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-142">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="7e6a5-143">Questa funzione viene usata per scorrere le gerarchie di directory e accetta un puntatore a una funzione come uno dei propri parametri.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-143">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="7e6a5-144">Tale funzione ha la firma seguente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-144">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

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

<span data-ttu-id="7e6a5-145">Nell'esempio macOS viene usata la stessa funzione. L'unica differenza è l'argomento dell'attributo `DllImport`, dal momento che macOS mantiene `libc` in una posizione differente.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-145">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

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
        // represents that struct in managed code.
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

<span data-ttu-id="7e6a5-146">Entrambi gli esempi precedenti dipendono da parametri e in entrambi i casi i parametri vengono forniti come tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-146">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="7e6a5-147">Il runtime esegue le operazioni necessarie ed elabora i parametri ottenendo i relativi equivalenti sull'altro lato.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-147">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="7e6a5-148">Informazioni su come i tipi sono sottoposti a marshalling in codice nativo sono disponibili nella pagina sul [marshalling dei tipi](type-marshalling.md).</span><span class="sxs-lookup"><span data-stu-id="7e6a5-148">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>


## <a name="more-resources"></a><span data-ttu-id="7e6a5-149">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="7e6a5-149">More resources</span></span>

*   <span data-ttu-id="7e6a5-150">[PInvoke.net wiki](https://www.pinvoke.net/): accurata pagina wiki con informazioni sulle API Win32 più comuni e sul modo di richiamarle.</span><span class="sxs-lookup"><span data-stu-id="7e6a5-150">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="7e6a5-151">P/Invoke in MSDN</span><span class="sxs-lookup"><span data-stu-id="7e6a5-151">P/Invoke on MSDN</span></span>](/cpp/dotnet/native-and-dotnet-interoperability)
*   [<span data-ttu-id="7e6a5-152">Documentazione su Mono in P/Invoke</span><span class="sxs-lookup"><span data-stu-id="7e6a5-152">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
