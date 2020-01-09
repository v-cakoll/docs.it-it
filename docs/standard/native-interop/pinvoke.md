---
title: Platform Invoke (P/Invoke)
description: Informazioni su come chiamare funzioni native tramite P/Invoke in .NET.
ms.date: 01/18/2019
ms.openlocfilehash: fa8b43edfba50fbc620f257c4e7caf1673f83235
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706305"
---
# <a name="platform-invoke-pinvoke"></a>Platform Invoke (P/Invoke)

P/Invoke è una tecnologia che consente di accedere dal codice gestito a struct, callback e funzioni presenti in librerie non gestite. La maggior parte delle API di P/Invoke è contenuta in due spazi dei nomi: `System` e `System.Runtime.InteropServices`. Usando questi due spazi dei nomi si ottengono gli strumenti per descrivere il modo in cui si vuole comunicare con il componente nativo.

Per iniziare viene mostrato l'esempio più comune, ovvero la chiamata di funzioni non gestite nel codice gestito. Di seguito viene visualizzata una finestra di messaggio da un'applicazione della riga di comando:

[!code-csharp[MessageBox](~/samples/snippets/standard/interop/pinvoke/messagebox.cs)]

L'esempio precedente è semplice, ma mostra chiaramente gli elementi necessari per richiamare funzioni non gestite da codice gestito. Di seguito l'esempio viene descritto in modo dettagliato:

- La riga 1 mostra l'istruzione using per lo spazio dei nomi `System.Runtime.InteropServices` contenente tutti gli elementi necessari.
- La riga 7 introduce l'attributo `DllImport`. Questo attributo è fondamentale, in quanto comunica al runtime che deve caricare la DLL non gestita. La stringa passata è la DLL che contiene la funzione di destinazione. Specifica anche quale [set di caratteri](./charset.md) usare per il marshalling delle stringhe. Indica infine che questa funzione chiama [SetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-setlasterror) e che il runtime deve acquisire il codice di errore in modo che l'utente possa recuperarlo tramite <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error?displayProperty=nameWithType>.
- La riga 8 è il punto cruciale dell'attività di P/Invoke. Definisce un metodo gestito che ha **esattamente la stessa firma** del metodo non gestito. Come è possibile notare, la dichiarazione dispone di una nuova parola chiave, `extern`, che indica al runtime che si tratta di un metodo esterno. Quando si richiama tale metodo, il runtime dovrebbe individuarlo nella DLL specificata nell'attributo `DllImport`.

La restante parte dell'esempio è semplicemente la chiamata del metodo, analoga alla chiamata di qualsiasi altro metodo gestito.

L'esempio è simile per macOS. Il nome della libreria nell'attributo `DllImport` deve essere modificato perché macOS usa uno schema diverso di denominazione delle librerie dinamiche. L'esempio seguente usa la funzione `getpid(2)` per ottenere l'ID processo dell'applicazione e stamparlo nella console:

[!code-csharp[getpid macOS](~/samples/snippets/standard/interop/pinvoke/getpid-macos.cs)]

È simile anche in Linux. Il nome della funzione è lo stesso, dal momento che `getpid(2)` è una chiamata di sistema [POSIX](https://en.wikipedia.org/wiki/POSIX) standard.

[!code-csharp[getpid Linux](~/samples/snippets/standard/interop/pinvoke/getpid-linux.cs)]

## <a name="invoking-managed-code-from-unmanaged-code"></a>Richiamare codice gestito da codice non gestito

Il runtime consente la comunicazione in entrambe le direzioni, permettendo il callback in codice gestito da funzioni native usando puntatori alle funzioni. In un codice gestito l'elemento più simile a un puntatore a funzione è un **delegato**. Viene quindi usato un delegato per consentire i callback dal codice nativo al codice gestito.

La modalità di uso di questa funzionalità è simile al processo di passaggio dal codice gestito a quello nativo descritto in precedenza. Per un determinato callback, viene definito un delegato corrispondente alla firma e tale delegato viene quindi passato al metodo esterno. Il runtime eseguirà tutte le altre operazioni.

[!code-csharp[EnumWindows](~/samples/snippets/standard/interop/pinvoke/enumwindows.cs)]

Prima di analizzare l'esempio, è opportuno esaminare le firme delle funzioni non gestite che è necessario utilizzare. La firma della funzione da chiamare per enumerare tutte le finestre è la seguente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

Il primo parametro è un callback. La firma di tale callback è la seguente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

A questo punto, è possibile esaminare l'esempio:

- La riga 9 nell'esempio definisce un delegato che corrisponde alla firma del callback da codice non gestito. Si noti che i tipi LPARAM e HWND vengono rappresentati usando `IntPtr` nel codice gestito.
- Le righe 13 e 14 introducono la funzione `EnumWindows` dalla libreria user32.dll.
- Le righe da 17 a 20 implementano il delegato. Per questo semplice esempio si vuole eseguire l'output dell'handle alla console.
- Nella riga 24, infine, il metodo esterno viene chiamato e passato al delegato.

Gli esempi Linux e macOS sono riportati di seguito. Per questi esempi viene usata la funzione `ftw` disponibile in `libc`, la libreria C. Questa funzione viene usata per scorrere le gerarchie di directory e accetta un puntatore a una funzione come uno dei propri parametri. Tale funzione ha la firma seguente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

[!code-csharp[ftw Linux](~/samples/snippets/standard/interop/pinvoke/ftw-linux.cs)]

Nell'esempio macOS viene usata la stessa funzione. L'unica differenza è l'argomento dell'attributo `DllImport`, dal momento che macOS mantiene `libc` in una posizione differente.

[!code-csharp[ftw macOS](~/samples/snippets/standard/interop/pinvoke/ftw-macos.cs)]

Entrambi gli esempi precedenti dipendono da parametri e in entrambi i casi i parametri vengono forniti come tipi gestiti. Il runtime esegue le operazioni necessarie ed elabora i parametri ottenendo i relativi equivalenti sull'altro lato. Sono disponibili informazioni su come i tipi sono sottoposti a marshalling in codice nativo nella pagina [Type marshaling](type-marshaling.md) (Marshalling dei tipi).

## <a name="more-resources"></a>Altre risorse

- [PInvoke.net wiki](https://www.pinvoke.net/): accurata pagina wiki con informazioni sulle API Windows comuni e sul modo di richiamarle.
- [P/Invoke in C++/CLI](/cpp/dotnet/native-and-dotnet-interoperability)
- [Documentazione su Mono in P/Invoke](https://www.mono-project.com/docs/advanced/pinvoke/)
