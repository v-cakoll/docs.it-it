---
title: Platform Invoke (P/Invoke)
description: Informazioni su come chiamare funzioni native tramite P/Invoke in .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: f243fee2b246afff36732d469c6295d7e4b2fd87
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411415"
---
# <a name="platform-invoke-pinvoke"></a>Platform Invoke (P/Invoke)

P/Invoke è una tecnologia che consente di accedere dal codice gestito a struct, callback e funzioni presenti in librerie non gestite. La maggior parte delle API di P/Invoke è contenuta in due spazi dei nomi: `System` e `System.Runtime.InteropServices`. Usando questi due spazi dei nomi si ottengono gli strumenti per descrivere il modo in cui si vuole comunicare con il componente nativo.

Per iniziare viene mostrato l'esempio più comune, ovvero la chiamata di funzioni non gestite nel codice gestito. Di seguito viene visualizzata una finestra di messaggio da un'applicazione della riga di comando:

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

L'esempio precedente è semplice, ma mostra chiaramente gli elementi necessari per richiamare funzioni non gestite da codice gestito. Di seguito l'esempio viene descritto in modo dettagliato:

*   La riga 1 mostra l'istruzione using per lo spazio dei nomi `System.Runtime.InteropServices` contenente tutti gli elementi necessari.
*   La riga 7 introduce l'attributo `DllImport`. Questo attributo è fondamentale, in quanto comunica al runtime che deve caricare la DLL non gestita. La stringa passata è la DLL che contiene la funzione di destinazione.
*   La riga 8 è il punto cruciale dell'attività di P/Invoke. Definisce un metodo gestito che ha **esattamente la stessa firma** del metodo non gestito. Come è possibile notare, la dichiarazione dispone di una nuova parola chiave, `extern`, che indica al runtime che si tratta di un metodo esterno. Quando si richiama tale metodo, il runtime dovrebbe individuarlo nella DLL specificata nell'attributo `DllImport`.

La restante parte dell'esempio è semplicemente la chiamata del metodo, analoga alla chiamata di qualsiasi altro metodo gestito.

L'esempio è simile per macOS. Il nome della libreria nell'attributo `DllImport` deve essere modificato perché macOS usa uno schema diverso di denominazione delle librerie dinamiche. L'esempio seguente usa la funzione `getpid(2)` per ottenere l'ID processo dell'applicazione e stamparlo nella console:

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

È simile anche in Linux. Il nome della funzione è lo stesso, dal momento che `getpid(2)` è una chiamata di sistema [POSIX](https://en.wikipedia.org/wiki/POSIX) standard.

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

## <a name="invoking-managed-code-from-unmanaged-code"></a>Richiamare codice gestito da codice non gestito

Il runtime consente la comunicazione in entrambe le direzioni, permettendo il callback in codice gestito da funzioni native usando puntatori alle funzioni. In un codice gestito l'elemento più simile a un puntatore a funzione è un **delegato**. Viene quindi usato un delegato per consentire i callback dal codice nativo al codice gestito.

La modalità di uso di questa funzionalità è simile al processo di passaggio dal codice gestito a quello nativo descritto in precedenza. Per un determinato callback, viene definito un delegato corrispondente alla firma e tale delegato viene quindi passato al metodo esterno. Il runtime eseguirà tutte le altre operazioni.

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

Prima di analizzare l'esempio, è opportuno esaminare le firme delle funzioni non gestite che è necessario utilizzare. La firma della funzione da chiamare per enumerare tutte le finestre è la seguente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

Il primo parametro è un callback. La firma di tale callback è la seguente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

A questo punto, è possibile esaminare l'esempio:

*   La riga 9 nell'esempio definisce un delegato che corrisponde alla firma del callback da codice non gestito. Si noti che i tipi LPARAM e HWND vengono rappresentati usando `IntPtr` nel codice gestito.
*   Le righe 13 e 14 introducono la funzione `EnumWindows` dalla libreria user32.dll.
*   Le righe da 17 a 20 implementano il delegato. Per questo semplice esempio si vuole eseguire l'output dell'handle alla console.
*   Nella riga 24, infine, il metodo esterno viene chiamato e passato al delegato.

Gli esempi Linux e macOS sono riportati di seguito. Per questi esempi viene usata la funzione `ftw` disponibile in `libc`, la libreria C. Questa funzione viene usata per scorrere le gerarchie di directory e accetta un puntatore a una funzione come uno dei propri parametri. Tale funzione ha la firma seguente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

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

Nell'esempio macOS viene usata la stessa funzione. L'unica differenza è l'argomento dell'attributo `DllImport`, dal momento che macOS mantiene `libc` in una posizione differente.

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

Entrambi gli esempi precedenti dipendono da parametri e in entrambi i casi i parametri vengono forniti come tipi gestiti. Il runtime esegue le operazioni necessarie ed elabora i parametri ottenendo i relativi equivalenti sull'altro lato. Informazioni su come i tipi sono sottoposti a marshalling in codice nativo sono disponibili nella pagina sul [marshalling dei tipi](type-marshalling.md).


## <a name="more-resources"></a>Altre risorse

*   [PInvoke.net wiki](https://www.pinvoke.net/): accurata pagina wiki con informazioni sulle API Win32 più comuni e sul modo di richiamarle.
*   [P/Invoke in MSDN](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [Documentazione su Mono in P/Invoke](https://www.mono-project.com/docs/advanced/pinvoke/)
