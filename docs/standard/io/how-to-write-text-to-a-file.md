---
title: 'Procedura: Scrivere un testo in un file'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9c637d9842c05f47bfcaa0431dd2f9f1ee29cc09
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50181238"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="0ea36-102">Procedura: Scrivere un testo in un file</span><span class="sxs-lookup"><span data-stu-id="0ea36-102">How to: Write Text to a File</span></span>
<span data-ttu-id="0ea36-103">Questo argomento illustra diverse modalità con cui è possibile scrivere un testo in un file per le applicazioni .NET Framework o le app di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea36-103">This topic shows different ways you can write text to a file for .NET Framework applications or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="0ea36-104">Per scrivere un testo in un file vengono in genere usati le classi e i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ea36-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
-   <span data-ttu-id="0ea36-105"><xref:System.IO.StreamWriter> : contiene i metodi per scrivere in un file in modo sincrono (<xref:System.IO.StreamWriter.Write%2A> o <xref:System.IO.TextWriter.WriteLine%2A>) o in modo asincrono (<xref:System.IO.StreamWriter.WriteAsync%2A> e <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="0ea36-105"><xref:System.IO.StreamWriter> - it contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> or <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
-   <span data-ttu-id="0ea36-106"><xref:System.IO.File> : da usare con le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ea36-106"><xref:System.IO.File> – to be used with .NET Framework applications.</span></span> <span data-ttu-id="0ea36-107">Fornisce i metodi statici per scrivere un testo in un file, ad esempio <xref:System.IO.File.WriteAllLines%2A> e <xref:System.IO.File.WriteAllText%2A>, o per aggiungere un testo in un file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> o <xref:System.IO.File.AppendText%2A>).</span><span class="sxs-lookup"><span data-stu-id="0ea36-107">It provides static methods to write text to a file such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> or <xref:System.IO.File.AppendText%2A>).</span></span>  
  
-   <span data-ttu-id="0ea36-108"><xref:Windows.Storage.FileIO>: da usare con le app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ea36-108"><xref:Windows.Storage.FileIO> - to be used with [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="0ea36-109">Contiene metodi asincroni per scrivere testo in un file (<xref:Windows.Storage.FileIO.WriteLinesAsync%2A> o <xref:Windows.Storage.FileIO.WriteTextAsync%2A>) oppure per accodare testo in un file (<xref:Windows.Storage.FileIO.AppendLinesAsync%2A> o <xref:Windows.Storage.FileIO.AppendTextAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="0ea36-109">It contains asynchronous methods to write text to a file (<xref:Windows.Storage.FileIO.WriteLinesAsync%2A> or <xref:Windows.Storage.FileIO.WriteTextAsync%2A>) or to append text to a file (<xref:Windows.Storage.FileIO.AppendLinesAsync%2A> or <xref:Windows.Storage.FileIO.AppendTextAsync%2A>).</span></span>  

- <span data-ttu-id="0ea36-110"><xref:System.IO.Path>: da usare per su stringhe che contengono informazioni sul percorso di file o directory.</span><span class="sxs-lookup"><span data-stu-id="0ea36-110"><xref:System.IO.Path> - to be used on strings that contain file or directory path information.</span></span> <span data-ttu-id="0ea36-111">Contiene il metodo <xref:System.IO.Path.Combine%2A>, che consente la concatenazione di stringhe per compilare un percorso di file o directory.</span><span class="sxs-lookup"><span data-stu-id="0ea36-111">It contains the <xref:System.IO.Path.Combine%2A> method, which allows concatenation of strings to build a file or directory path.</span></span>


 <span data-ttu-id="0ea36-112">Gli esempi sono semplici per concentrarsi sull'attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="0ea36-112">The samples have been kept simple in order to focus on the task being performed.</span></span> <span data-ttu-id="0ea36-113">Per questo motivo, gli esempi eseguono eventualmente delle procedure minime di controllo degli errori e di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0ea36-113">For this reason, the samples perform minimal error checking and exception handling, if any.</span></span> <span data-ttu-id="0ea36-114">Un'applicazione reale fornisce in genere procedure di controllo degli errori e di gestione delle eccezioni più efficaci.</span><span class="sxs-lookup"><span data-stu-id="0ea36-114">A real-world application generally provides more robust error checking and exception handling.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ea36-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ea36-115">Example</span></span>  
 <span data-ttu-id="0ea36-116">L'esempio seguente illustra come scrivere in modo sincrono un testo una riga alla volta in un nuovo file usando la classe <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="0ea36-116">The following example shows how to synchronously write text to a new file using the <xref:System.IO.StreamWriter> class, one line at a time.</span></span> <span data-ttu-id="0ea36-117">Il nuovo file di testo viene salvato nella cartella Documenti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0ea36-117">The new text file is saved to the user's My Documents folder.</span></span> <span data-ttu-id="0ea36-118">Poiché l'oggetto <xref:System.IO.StreamWriter> viene dichiarato in un'istruzione `using` in cui viene creata anche un'istanza dell'oggetto stesso, viene richiamato il metodo <xref:System.IO.StreamWriter.Dispose%2A> che scarica e chiude automaticamente il flusso.</span><span class="sxs-lookup"><span data-stu-id="0ea36-118">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked which automatically flushes and closes the stream.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a><span data-ttu-id="0ea36-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ea36-119">Example</span></span>  
 <span data-ttu-id="0ea36-120">L'esempio seguente illustra come aggiungere un testo in un file esistente usando la classe <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="0ea36-120">The following example shows how to append text to an existing file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="0ea36-121">Viene usato lo stesso file di testo dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="0ea36-121">It uses the same text file from the previous example.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a><span data-ttu-id="0ea36-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ea36-122">Example</span></span>  
 <span data-ttu-id="0ea36-123">L'esempio seguente illustra come scrivere in modo asincrono un testo in un nuovo file usando la classe <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="0ea36-123">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="0ea36-124">Per richiamare il metodo <xref:System.IO.StreamWriter.WriteAsync%2A> , la chiamata al metodo deve essere eseguita all'interno di un metodo `async` .</span><span class="sxs-lookup"><span data-stu-id="0ea36-124">In order to invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call needs to be within an `async` method.</span></span> <span data-ttu-id="0ea36-125">Il nuovo file di testo viene salvato nella cartella Documenti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0ea36-125">The new text file is saved to the user's My Documents folder.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a><span data-ttu-id="0ea36-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ea36-126">Example</span></span>  
 <span data-ttu-id="0ea36-127">L'esempio seguente illustra come scrivere un testo in un nuovo file e aggiungere nuove righe di testo nello stesso file usando la classe <xref:System.IO.File> .</span><span class="sxs-lookup"><span data-stu-id="0ea36-127">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="0ea36-128">I metodi <xref:System.IO.File.WriteAllText%2A> e <xref:System.IO.File.AppendAllLines%2A> aprono e chiudono automaticamente il file.</span><span class="sxs-lookup"><span data-stu-id="0ea36-128">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="0ea36-129">Se il percorso fornito al metodo <xref:System.IO.File.WriteAllText%2A> esiste già, il file verrà sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="0ea36-129">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file will be overwritten.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a><span data-ttu-id="0ea36-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ea36-130">Example</span></span>  
 <span data-ttu-id="0ea36-131">L'esempio seguente mostra come scrivere l'input dell'utente in modo asincrono in un file di testo di un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ea36-131">The following example shows how to asynchronously write user input to a text file in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="0ea36-132">Per motivi di sicurezza, l'apertura di un file da un'app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] richiede in genere l'uso di un controllo <xref:Windows.Storage.Pickers.FileOpenPicker>.</span><span class="sxs-lookup"><span data-stu-id="0ea36-132">Because of security considerations, opening a file from a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app typically requires the use of a <xref:Windows.Storage.Pickers.FileOpenPicker> control.</span></span> <span data-ttu-id="0ea36-133">In questo esempio, `FileOpenPicker` è filtrato per mostrare i file di testo.</span><span class="sxs-lookup"><span data-stu-id="0ea36-133">In this example, the `FileOpenPicker` is filtered to show text files.</span></span>  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## <a name="see-also"></a><span data-ttu-id="0ea36-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ea36-134">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.Path>  
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="0ea36-135">Procedura: Enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="0ea36-135">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="0ea36-136">Procedura: Leggere e scrivere su un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="0ea36-136">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="0ea36-137">Procedura: Aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="0ea36-137">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="0ea36-138">Procedura: Leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="0ea36-138">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="0ea36-139">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="0ea36-139">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
