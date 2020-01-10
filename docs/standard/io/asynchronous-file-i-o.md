---
title: I/O di file asincrono
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET Framework], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
ms.openlocfilehash: 66e7d01f37a1119b9d2076a9131aa40f26d15625
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708191"
---
# <a name="asynchronous-file-io"></a><span data-ttu-id="78ee4-102">I/O di file asincrono</span><span class="sxs-lookup"><span data-stu-id="78ee4-102">Asynchronous File I/O</span></span>

<span data-ttu-id="78ee4-103">Le operazioni asincrone consentono di eseguire operazioni di I/O a elevato utilizzo di risorse senza bloccare il thread principale.</span><span class="sxs-lookup"><span data-stu-id="78ee4-103">Asynchronous operations enable you to perform resource-intensive I/O operations without blocking the main thread.</span></span> <span data-ttu-id="78ee4-104">Questa considerazione sulle prestazioni è particolarmente importante in un'app di Windows 8. x Store o in un'app desktop in cui un'operazione di flusso che richiede molto tempo può bloccare il thread dell'interfaccia utente e fare in modo che l'app appaia come se non fosse funzionante.</span><span class="sxs-lookup"><span data-stu-id="78ee4-104">This performance consideration is particularly important in a Windows 8.x Store app or desktop app where a time-consuming stream operation can block the UI thread and make your app appear as if it is not working.</span></span>

<span data-ttu-id="78ee4-105">A partire da .NET Framework 4.5, i tipi di I/O includono metodi async per semplificare le operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="78ee4-105">Starting with the .NET Framework 4.5, the I/O types include async methods to simplify asynchronous operations.</span></span> <span data-ttu-id="78ee4-106">Un metodo asincrono contiene `Async` nel nome, ad esempio <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>e <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="78ee4-106">An async method contains `Async` in its name, such as <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>, and <xref:System.IO.TextReader.ReadToEndAsync%2A>.</span></span> <span data-ttu-id="78ee4-107">Questi metodi asincroni sono implementati nelle classi di flusso, come <xref:System.IO.Stream>, <xref:System.IO.FileStream>e <xref:System.IO.MemoryStream>, e nelle classi usate per la lettura o la scrittura nei flussi, come <xref:System.IO.TextReader> e <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="78ee4-107">These async methods are implemented on stream classes, such as <xref:System.IO.Stream>, <xref:System.IO.FileStream>, and <xref:System.IO.MemoryStream>, and on classes that are used for reading from or writing to streams, such <xref:System.IO.TextReader> and <xref:System.IO.TextWriter>.</span></span>

<span data-ttu-id="78ee4-108">In .NET Framework 4 e versioni precedenti è necessario usare metodi quali <xref:System.IO.Stream.BeginRead%2A> e <xref:System.IO.Stream.EndRead%2A> per implementare operazioni di I/O asincrone.</span><span class="sxs-lookup"><span data-stu-id="78ee4-108">In the .NET Framework 4 and earlier versions, you have to use methods such as <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> to implement asynchronous I/O operations.</span></span> <span data-ttu-id="78ee4-109">Questi metodi sono ancora disponibili in .NET Framework 4.5 per supportare il codice legacy. Tuttavia, i metodi async consentono di implementare più facilmente le operazioni di I/O asincrone.</span><span class="sxs-lookup"><span data-stu-id="78ee4-109">These methods are still available in the .NET Framework 4.5 to support legacy code; however, the async methods help you implement asynchronous I/O operations more easily.</span></span>

<span data-ttu-id="78ee4-110">C# e Visual Basic hanno ognuno due parole chiave per la programmazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="78ee4-110">C# and Visual Basic each have two keywords for asynchronous programming:</span></span>

- <span data-ttu-id="78ee4-111">Il modificatore`Async` (Visual Basic) o `async` (C#), che viene usato per contrassegnare un metodo contenente un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="78ee4-111">`Async` (Visual Basic) or `async` (C#) modifier, which is used to mark a method that contains an asynchronous operation.</span></span>

- <span data-ttu-id="78ee4-112">L'operatore`Await` (Visual Basic) o `await` (C#), che viene applicato al risultato di un metodo async.</span><span class="sxs-lookup"><span data-stu-id="78ee4-112">`Await` (Visual Basic) or `await` (C#) operator, which is applied to the result of an async method.</span></span>

<span data-ttu-id="78ee4-113">Per implementare le operazioni di I/O asincrone, usare queste parole chiave con i metodi async, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="78ee4-113">To implement asynchronous I/O operations, use these keywords in conjunction with the async methods, as shown in the following examples.</span></span> <span data-ttu-id="78ee4-114">Per altre informazioni, vedere [Programmazione asincrona con async e await (C#)](../../csharp/programming-guide/concepts/async/index.md) o [Programmazione asincrona con Async e Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="78ee4-114">For more information, see [Asynchronous programming with async and await (C#)](../../csharp/programming-guide/concepts/async/index.md) or [Asynchronous Programming with Async and Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="78ee4-115">L'esempio seguente mostra come usare due oggetti <xref:System.IO.FileStream> per copiare i file in modo asincrono da una directory a un'altra.</span><span class="sxs-lookup"><span data-stu-id="78ee4-115">The following example demonstrates how to use two <xref:System.IO.FileStream> objects to copy files asynchronously from one directory to another.</span></span> <span data-ttu-id="78ee4-116">Si noti che il gestore eventi <xref:System.Web.UI.WebControls.Button.Click> per il controllo <xref:System.Windows.Controls.Button> è contrassegnato con il modificatore `async` perché chiama un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="78ee4-116">Notice that the <xref:System.Web.UI.WebControls.Button.Click> event handler for the <xref:System.Windows.Controls.Button> control is marked with the `async` modifier because it calls an asynchronous method.</span></span>

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

<span data-ttu-id="78ee4-117">L'esempio seguente è simile a quello precedente ma usa gli oggetti <xref:System.IO.StreamReader> e <xref:System.IO.StreamWriter> per leggere e scrivere il contenuto di un file di testo in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="78ee4-117">The next example is similar to the previous one but uses <xref:System.IO.StreamReader> and <xref:System.IO.StreamWriter> objects to read and write the contents of a text file asynchronously.</span></span>

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

<span data-ttu-id="78ee4-118">L'esempio seguente mostra il file code-behind e il file XAML usati per aprire un file come <xref:System.IO.Stream> in un'app di Windows 8. x Store e leggerne il contenuto usando un'istanza della classe <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="78ee4-118">The next example shows the code-behind file and the XAML file that are used to open a file as a <xref:System.IO.Stream> in a Windows 8.x Store app, and read its contents by using an instance of the <xref:System.IO.StreamReader> class.</span></span> <span data-ttu-id="78ee4-119">Usa i metodi asincroni per aprire il file come flusso e leggerne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="78ee4-119">It uses asynchronous methods to open the file as a stream and to read its contents.</span></span>

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="78ee4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78ee4-120">See also</span></span>

- <xref:System.IO.Stream>
- [<span data-ttu-id="78ee4-121">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="78ee4-121">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="78ee4-122">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="78ee4-122">Asynchronous programming with async and await (C#)</span></span>](../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="78ee4-123">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78ee4-123">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
