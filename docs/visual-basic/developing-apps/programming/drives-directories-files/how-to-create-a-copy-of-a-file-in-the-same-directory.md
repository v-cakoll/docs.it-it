---
title: 'Procedura: creare una copia di un file nella stessa directory in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- File.Copy
dev_langs:
- VB
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files, copying
- CopyFile method, copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
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
ms.openlocfilehash: 7e15b85a72c9b2504551174f5b104bdbb01cf3f3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a><span data-ttu-id="db045-102">Procedura: creare una copia di un file nella stessa directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db045-102">How to: Create a Copy of a File in the Same Directory in Visual Basic</span></span>
<span data-ttu-id="db045-103">Usare il metodo `My.Computer.FileSystem.CopyFile` per copiare i file.</span><span class="sxs-lookup"><span data-stu-id="db045-103">Use the `My.Computer.FileSystem.CopyFile` method to copy files.</span></span> <span data-ttu-id="db045-104">I parametri consentono di sovrascrivere file esistenti, rinominare il file, visualizzare lo stato di avanzamento dell'operazione e permettere all'utente di annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="db045-104">The parameters allow you to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a><span data-ttu-id="db045-105">Per creare una copia di un file nella stessa directory</span><span class="sxs-lookup"><span data-stu-id="db045-105">To create a copy of a file in the same folder</span></span>  
  
-   <span data-ttu-id="db045-106">Usare il metodo `CopyFile` specificando il percorso e il file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db045-106">Use the `CopyFile` method, supplying the target file and the location.</span></span> <span data-ttu-id="db045-107">Nell'esempio seguente viene creata una copia di `test2.txt` denominata `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="db045-107">The following example creates a copy of `test.txt` called `test2.txt`.</span></span>  
  
     <span data-ttu-id="db045-108">[!code-vb[VbVbcnMyFileSystem#51](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="db045-108">[!code-vb[VbVbcnMyFileSystem#51](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_1.vb)]</span></span>  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a><span data-ttu-id="db045-109">Per creare una copia di un file nella stessa cartella, sovrascrivendo i file esistenti</span><span class="sxs-lookup"><span data-stu-id="db045-109">To create a copy of a file in the same folder, overwriting existing files</span></span>  
  
-   <span data-ttu-id="db045-110">Usare il metodo `CopyFile` specificando il percorso e il file di destinazione e impostando `overwrite` su `True`.</span><span class="sxs-lookup"><span data-stu-id="db045-110">Use the `CopyFile` method, supplying the target file and location, and setting `overwrite` to `True`.</span></span> <span data-ttu-id="db045-111">Nell'esempio riportato di seguito viene creata una copia di `test.txt` denominata `test2.txt` e i file esistenti vengono sovrascritti con questo nome.</span><span class="sxs-lookup"><span data-stu-id="db045-111">The following example creates a copy of `test.txt` called `test2.txt` and overwrites any existing files by that name.</span></span>  
  
     <span data-ttu-id="db045-112">[!code-vb[VbVbcnMyFileSystem#52](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="db045-112">[!code-vb[VbVbcnMyFileSystem#52](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-the-same-directory_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="db045-113">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="db045-113">Robust Programming</span></span>  
 <span data-ttu-id="db045-114">Le condizioni seguenti possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="db045-114">The following conditions may cause an exception to be thrown:</span></span>  
  
-   <span data-ttu-id="db045-115">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="db045-115">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="db045-116">Il sistema non ha recuperato il percorso assoluto (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="db045-116">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="db045-117">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="db045-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="db045-118">Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="db045-118">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="db045-119">Il percorso combinato punta a una directory esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="db045-119">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="db045-120">Il file di destinazione esiste e `overwrite` è impostato su `False` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="db045-120">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="db045-121">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="db045-121">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="db045-122">Un file nella cartella di destinazione con lo stesso nome è in uso (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="db045-122">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="db045-123">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="db045-123">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="db045-124">`ShowUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e l'utente ha annullato l'operazione (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="db045-124">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="db045-125">`ShowUI`è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e si verifica un errore di I/O non specificato (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="db045-125">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="db045-126">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="db045-126">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="db045-127">L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="db045-127">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="db045-128">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="db045-128">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db045-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db045-129">See Also</span></span>  
 <span data-ttu-id="db045-130"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="db045-130"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="db045-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span><span class="sxs-lookup"><span data-stu-id="db045-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span></span>   
 <span data-ttu-id="db045-132"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span><span class="sxs-lookup"><span data-stu-id="db045-132"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span></span>   
 <span data-ttu-id="db045-133">[Procedura: Copiare file con un criterio specifico in una directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md) </span><span class="sxs-lookup"><span data-stu-id="db045-133">[How to: Copy Files with a Specific Pattern to a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md) </span></span>  
 <span data-ttu-id="db045-134">[Procedura: Creare una copia di un file in una directory diversa](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md) </span><span class="sxs-lookup"><span data-stu-id="db045-134">[How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md) </span></span>  
 <span data-ttu-id="db045-135">[Procedura: Copiare una directory in un'altra directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md) </span><span class="sxs-lookup"><span data-stu-id="db045-135">[How to: Copy a Directory to Another Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md) </span></span>  
 [<span data-ttu-id="db045-136">Procedura: rinominare un file</span><span class="sxs-lookup"><span data-stu-id="db045-136">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)

