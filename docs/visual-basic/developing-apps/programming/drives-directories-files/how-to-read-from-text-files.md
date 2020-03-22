---
title: 'Procedura: leggere da file di testoHow to: Read From Text Files'
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 8af088ad269cc77bc5c83aedb86bde9af2e37a15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334583"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a><span data-ttu-id="2b23c-102">Procedura: leggere da file di testo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b23c-102">How to: Read From Text Files in Visual Basic</span></span>

<span data-ttu-id="2b23c-103">Il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> dell'oggetto `My.Computer.FileSystem` consente la lettura di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2b23c-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> method of the `My.Computer.FileSystem` object allows you to read from a text file.</span></span> <span data-ttu-id="2b23c-104">È possibile specificare la codifica file se il contenuto del file utilizza, ad esempio, la codifica ASCII o UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2b23c-104">The file encoding can be specified if the contents of the file use an encoding such as ASCII or UTF-8.</span></span>

<span data-ttu-id="2b23c-105">Se la lettura è eseguita da un file contenente caratteri estesi, è necessario specificare la codifica del file.</span><span class="sxs-lookup"><span data-stu-id="2b23c-105">If you are reading from a file with extended characters, you will need to specify the file encoding.</span></span>

> [!NOTE]
> <span data-ttu-id="2b23c-106">Per leggere un file una riga di testo alla volta, utilizzare il metodo <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> dell'oggetto `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="2b23c-106">To read a file a single line of text at a time, use the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> method of the `My.Computer.FileSystem` object.</span></span> <span data-ttu-id="2b23c-107">Il metodo `OpenTextFileReader` restituisce un oggetto <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="2b23c-107">The `OpenTextFileReader` method returns a <xref:System.IO.StreamReader> object.</span></span> <span data-ttu-id="2b23c-108">È possibile utilizzare il metodo <xref:System.IO.StreamReader.ReadLine%2A> dell'oggetto `StreamReader` per leggere un file una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="2b23c-108">You can use the <xref:System.IO.StreamReader.ReadLine%2A> method of the `StreamReader` object to read a file one line at a time.</span></span> <span data-ttu-id="2b23c-109">È possibile eseguire il test della fine del file utilizzando il metodo <xref:System.IO.StreamReader.EndOfStream%2A> dell'oggetto `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="2b23c-109">You can test for the end of the file using the <xref:System.IO.StreamReader.EndOfStream%2A> method of the `StreamReader` object.</span></span>

## <a name="to-read-from-a-text-file"></a><span data-ttu-id="2b23c-110">Per leggere da un file di testo</span><span class="sxs-lookup"><span data-stu-id="2b23c-110">To read from a text file</span></span>

<span data-ttu-id="2b23c-111">Utilizzare il metodo `ReadAllText` dell'oggetto `My.Computer.FileSystem` per leggere il contenuto di un file di testo in una stringa, specificando il percorso.</span><span class="sxs-lookup"><span data-stu-id="2b23c-111">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path.</span></span> <span data-ttu-id="2b23c-112">Nell'esempio seguente viene letto il contenuto del file test.txt in una stringa e quindi tale contenuto viene visualizzato in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2b23c-112">The following example reads the contents of test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a><span data-ttu-id="2b23c-113">Per leggere da un file di testo codificato</span><span class="sxs-lookup"><span data-stu-id="2b23c-113">To read from a text file that is encoded</span></span>

<span data-ttu-id="2b23c-114">Utilizzare il metodo `ReadAllText` dell'oggetto `My.Computer.FileSystem` per leggere il contenuto di un file di testo in una stringa, specificando il percorso e il tipo di codifica file.</span><span class="sxs-lookup"><span data-stu-id="2b23c-114">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path and file encoding type.</span></span> <span data-ttu-id="2b23c-115">Nell'esempio seguente viene letto il contenuto del file test.txt UTF32 in una stringa e quindi tale contenuto viene visualizzato in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2b23c-115">The following example reads the contents of the UTF32 file test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a><span data-ttu-id="2b23c-116">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="2b23c-116">Robust Programming</span></span>

<span data-ttu-id="2b23c-117">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="2b23c-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="2b23c-118">Il percorso non è valido per uno dei seguenti motivi: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di una periferica (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-118">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="2b23c-119">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-119">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="2b23c-120">Il file non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-120">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>

- <span data-ttu-id="2b23c-121">Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-121">The file is in use by another process or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="2b23c-122">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="2b23c-123">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-123">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="2b23c-124">La memoria disponibile non è sufficiente per la scrittura della stringa nel buffer (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-124">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>

- <span data-ttu-id="2b23c-125">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="2b23c-125">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

<span data-ttu-id="2b23c-126">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="2b23c-126">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="2b23c-127">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2b23c-127">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>

<span data-ttu-id="2b23c-128">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="2b23c-128">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="2b23c-129">È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2b23c-129">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b23c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b23c-130">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [<span data-ttu-id="2b23c-131">Lettura da file</span><span class="sxs-lookup"><span data-stu-id="2b23c-131">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="2b23c-132">Procedura: leggere file di testo delimitati da virgola</span><span class="sxs-lookup"><span data-stu-id="2b23c-132">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="2b23c-133">Procedura: leggere file di testo a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="2b23c-133">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="2b23c-134">Procedura: leggere file di testo con più formati</span><span class="sxs-lookup"><span data-stu-id="2b23c-134">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="2b23c-135">Risoluzione dei problemi: lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="2b23c-135">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="2b23c-136">Procedura dettagliata: Modifica di file e directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b23c-136">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="2b23c-137">Codifiche dei file</span><span class="sxs-lookup"><span data-stu-id="2b23c-137">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
