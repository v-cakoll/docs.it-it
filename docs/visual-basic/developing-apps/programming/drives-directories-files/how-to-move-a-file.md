---
title: 'Procedura: spostare un file in Visual Basic'
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
- files, moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5a2623ec7e440e8fdf85138cd0b3de9ab18b773c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-move-a-file-in-visual-basic"></a><span data-ttu-id="81c0d-102">Procedura: spostare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81c0d-102">How to: Move a File in Visual Basic</span></span>
<span data-ttu-id="81c0d-103">Il metodo `My.Computer.FileSystem.MoveFile` consente di spostare un file in una cartella diversa.</span><span class="sxs-lookup"><span data-stu-id="81c0d-103">The `My.Computer.FileSystem.MoveFile` method can be used to move a file to another folder.</span></span> <span data-ttu-id="81c0d-104">Se la struttura di destinazione non esiste, verrà creata.</span><span class="sxs-lookup"><span data-stu-id="81c0d-104">If the target structure does not exist, it will be created.</span></span>  
  
### <a name="to-move-a-file"></a><span data-ttu-id="81c0d-105">Per spostare un file</span><span class="sxs-lookup"><span data-stu-id="81c0d-105">To move a file</span></span>  
  
-   <span data-ttu-id="81c0d-106">Per spostare il file, usare il metodo `MoveFile` , specificando il nome e il percorso del file di origine e del file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="81c0d-106">Use the `MoveFile` method to move the file, specifying the file name and location for both the source file and the target file.</span></span> <span data-ttu-id="81c0d-107">In questo esempio il file `test.txt` viene spostato da `TestDir1` a `TestDir2`.</span><span class="sxs-lookup"><span data-stu-id="81c0d-107">This example moves the file named `test.txt` from `TestDir1` to `TestDir2`.</span></span> <span data-ttu-id="81c0d-108">Si noti che il nome del file di destinazione viene specificato anche se corrisponde al nome del file di origine.</span><span class="sxs-lookup"><span data-stu-id="81c0d-108">Note that the target file name is specified even though it is the same as the source file name.</span></span>  
  
     <span data-ttu-id="81c0d-109">[!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="81c0d-109">[!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_1.vb)]</span></span>  
  
### <a name="to-move-a-file-and-rename-it"></a><span data-ttu-id="81c0d-110">Per spostare un file e rinominarlo</span><span class="sxs-lookup"><span data-stu-id="81c0d-110">To move a file and rename it</span></span>  
  
-   <span data-ttu-id="81c0d-111">Per spostare il file, usare il metodo `MoveFile` , specificando il nome e il percorso del file di origine, il percorso di destinazione e il nome che si desidera assegnare al file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="81c0d-111">Use the `MoveFile` method to move the file, specifying the source file name and location, the target location, and the new name at the target location.</span></span> <span data-ttu-id="81c0d-112">In questo esempio il file `test.txt` viene spostato da `TestDir1` a `TestDir2` e viene rinominato `nexttest.txt`.</span><span class="sxs-lookup"><span data-stu-id="81c0d-112">This example moves the file named `test.txt` from `TestDir1` to `TestDir2` and renames it `nexttest.txt`.</span></span>  
  
     <span data-ttu-id="81c0d-113">[!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="81c0d-113">[!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="81c0d-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="81c0d-114">Robust Programming</span></span>  
 <span data-ttu-id="81c0d-115">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="81c0d-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="81c0d-116">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-116">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="81c0d-117">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="81c0d-118">`destinationFileName` è `Nothing` o una stringa vuota (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-118">`destinationFileName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="81c0d-119">Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-119">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="81c0d-120">Il percorso complessivo corrisponde a una directory esistente, il file di destinazione esiste e `overwrite` è impostato su `False`, un file con lo stesso nome è già in uso nella directory di destinazione oppure l'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-120">The combined path points to an existing directory, the destination file exists and `overwrite` is set to `False`, a file in the target directory with the same name is in use, or the user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="81c0d-121">Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-121">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="81c0d-122">`showUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException`e l'utente ha annullato l'operazione oppure si è verificato un errore di I/O non specificato (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-122">`showUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and either the user has cancelled the operation or an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="81c0d-123">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-123">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="81c0d-124">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="81c0d-125">L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="81c0d-125">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c0d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c0d-126">See Also</span></span>  
 <span data-ttu-id="81c0d-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A></span><span class="sxs-lookup"><span data-stu-id="81c0d-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A></span></span>   
 <span data-ttu-id="81c0d-128">[Procedura: Rinominare un file](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="81c0d-128">[How to: Rename a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md) </span></span>  
 <span data-ttu-id="81c0d-129">[Procedura: Creare una copia di un file in una directory diversa](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md) </span><span class="sxs-lookup"><span data-stu-id="81c0d-129">[How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md) </span></span>  
 [<span data-ttu-id="81c0d-130">Procedura: analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="81c0d-130">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

