---
title: 'Procedura: rinominare un file'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: e69dad9ad7f59002ad62b7a06299ff012488e534
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334547"
---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="c15e3-102">Procedura: rinominare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c15e3-102">How to: Rename a File in Visual Basic</span></span>

<span data-ttu-id="c15e3-103">Usare il metodo `RenameFile` dell'oggetto `My.Computer.FileSystem` per rinominare un file fornendo la posizione corrente, il nome file attuale e il nuovo nome file.</span><span class="sxs-lookup"><span data-stu-id="c15e3-103">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="c15e3-104">Questo metodo non può essere usato per spostare un file. Per spostare e rinominare un file, usare il metodo `MoveFile`.</span><span class="sxs-lookup"><span data-stu-id="c15e3-104">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="c15e3-105">Per rinominare un file</span><span class="sxs-lookup"><span data-stu-id="c15e3-105">To rename a file</span></span>  
  
- <span data-ttu-id="c15e3-106">Usare il metodo `My.Computer.FileSystem.RenameFile`per rinominare un file.</span><span class="sxs-lookup"><span data-stu-id="c15e3-106">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="c15e3-107">In questo esempio il file `Test.txt` viene rinominato in `SecondTest.txt`.</span><span class="sxs-lookup"><span data-stu-id="c15e3-107">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#9)]  
  
 <span data-ttu-id="c15e3-108">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c15e3-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c15e3-109">Nella casella di selezione dei frammenti di codice il frammento si trova in **File system - Elaborazione di unità, cartelle e file**.</span><span class="sxs-lookup"><span data-stu-id="c15e3-109">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="c15e3-110">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="c15e3-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c15e3-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c15e3-111">Robust Programming</span></span>  

 <span data-ttu-id="c15e3-112">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="c15e3-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c15e3-113">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="c15e3-114">`newName` contiene informazioni sul percorso (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-114">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="c15e3-115">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="c15e3-116">`newName` è `Nothing` o una stringa vuota (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-116">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="c15e3-117">Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="c15e3-118">Esiste un file o directory con il nome specificato in `newName` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-118">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="c15e3-119">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="c15e3-120">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="c15e3-121">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="c15e3-122">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="c15e3-122">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15e3-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c15e3-123">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>
- [<span data-ttu-id="c15e3-124">Procedura: spostare un file</span><span class="sxs-lookup"><span data-stu-id="c15e3-124">How to: Move a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)
- [<span data-ttu-id="c15e3-125">Creazione, eliminazione e spostamento di file e directory</span><span class="sxs-lookup"><span data-stu-id="c15e3-125">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
- [<span data-ttu-id="c15e3-126">Procedura: creare una copia di un file nella stessa directory</span><span class="sxs-lookup"><span data-stu-id="c15e3-126">How to: Create a Copy of a File in the Same Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="c15e3-127">Procedura: creare una copia di un file in una directory diversa</span><span class="sxs-lookup"><span data-stu-id="c15e3-127">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
