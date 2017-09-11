---
title: 'Procedura: rinominare un file in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files, renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f003cfc7c7880a47515f7328a0503072f3b02cbf
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="03b11-102">Procedura: rinominare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="03b11-102">How to: Rename a File in Visual Basic</span></span>
<span data-ttu-id="03b11-103">Usare il metodo `RenameFile` dell'oggetto `My.Computer.FileSystem` per rinominare un file fornendo la posizione corrente, il nome file attuale e il nuovo nome file.</span><span class="sxs-lookup"><span data-stu-id="03b11-103">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="03b11-104">Questo metodo non può essere usato per spostare un file. Per spostare e rinominare un file, usare il metodo `MoveFile`.</span><span class="sxs-lookup"><span data-stu-id="03b11-104">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="03b11-105">Per rinominare un file</span><span class="sxs-lookup"><span data-stu-id="03b11-105">To rename a file</span></span>  
  
-   <span data-ttu-id="03b11-106">Usare il metodo `My.Computer.FileSystem.RenameFile`per rinominare un file.</span><span class="sxs-lookup"><span data-stu-id="03b11-106">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="03b11-107">In questo esempio il file `Test.txt` viene rinominato in `SecondTest.txt`.</span><span class="sxs-lookup"><span data-stu-id="03b11-107">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     <span data-ttu-id="03b11-108">[!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03b11-108">[!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]</span></span>  
  
 <span data-ttu-id="03b11-109">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="03b11-109">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="03b11-110">Nella casella di selezione dei frammenti di codice il frammento si trova in **File system - Elaborazione di unità, cartelle e file**.</span><span class="sxs-lookup"><span data-stu-id="03b11-110">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="03b11-111">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="03b11-111">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="03b11-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="03b11-112">Robust Programming</span></span>  
 <span data-ttu-id="03b11-113">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="03b11-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="03b11-114">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="03b11-115">`newName` contiene informazioni sul percorso (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-115">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="03b11-116">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="03b11-117">`newName` è `Nothing` o una stringa vuota (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-117">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="03b11-118">Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-118">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="03b11-119">Esiste un file o directory con il nome specificato in `newName` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-119">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="03b11-120">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-120">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="03b11-121">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-121">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="03b11-122">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="03b11-123">L'utente non dispone delle autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="03b11-123">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b11-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03b11-124">See Also</span></span>  
 <span data-ttu-id="03b11-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A></span><span class="sxs-lookup"><span data-stu-id="03b11-125"><xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A></span></span>   
 <span data-ttu-id="03b11-126">[Procedura: Spostare un file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="03b11-126">[How to: Move a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md) </span></span>  
 <span data-ttu-id="03b11-127">[Creazione, eliminazione e spostamento di file e directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="03b11-127">[Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md) </span></span>  
 <span data-ttu-id="03b11-128">[Procedura: Creare una copia di un file nella stessa directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md) </span><span class="sxs-lookup"><span data-stu-id="03b11-128">[How to: Create a Copy of a File in the Same Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md) </span></span>  
 [<span data-ttu-id="03b11-129">Procedura: creare una copia di un file in una directory diversa</span><span class="sxs-lookup"><span data-stu-id="03b11-129">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)

