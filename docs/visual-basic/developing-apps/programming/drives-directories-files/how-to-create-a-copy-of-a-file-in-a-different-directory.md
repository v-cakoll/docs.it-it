---
title: 'Procedura: creare una copia di un file in una directory diversa in Visual Basic'
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
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files, copying
- CopyFile method, copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
caps.latest.revision: 17
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
ms.openlocfilehash: ef6fcfaa38343d0fb137571b82f4d2719f3d61ef
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a><span data-ttu-id="4ad03-102">Procedura: creare una copia di un file in una directory diversa in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ad03-102">How to: Create a Copy of a File in a Different Directory in Visual Basic</span></span>
<span data-ttu-id="4ad03-103">Il metodo `My.Computer.FileSystem.CopyFile` consente di copiare i file.</span><span class="sxs-lookup"><span data-stu-id="4ad03-103">The `My.Computer.FileSystem.CopyFile` method allows you to copy files.</span></span> <span data-ttu-id="4ad03-104">I sui parametri consentono di sovrascrivere file esistenti, rinominare il file, visualizzare lo stato di avanzamento dell'operazione e consentire all'utente di annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="4ad03-104">Its parameters provide the ability to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-copy-a-text-file-to-another-folder"></a><span data-ttu-id="4ad03-105">Per copiare un file di testo in un'altra cartella</span><span class="sxs-lookup"><span data-stu-id="4ad03-105">To copy a text file to another folder</span></span>  
  
-   <span data-ttu-id="4ad03-106">Usare il metodo `CopyFile` per copiare un file, specificando il file di origine e la directory di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4ad03-106">Use the `CopyFile` method to copy a file, specifying a source file and the target directory.</span></span> <span data-ttu-id="4ad03-107">Il parametro `overwrite` consente di specificare se sovrascrivere o meno i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="4ad03-107">The `overwrite` parameter allows you to specify whether or not to overwrite existing files.</span></span> <span data-ttu-id="4ad03-108">Negli esempi di codice seguenti viene illustrato l'uso di `CopyFile`.</span><span class="sxs-lookup"><span data-stu-id="4ad03-108">The following code examples demonstrate how to use `CopyFile`.</span></span>  
  
     <span data-ttu-id="4ad03-109">[!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4ad03-109">[!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4ad03-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="4ad03-110">Robust Programming</span></span>  
 <span data-ttu-id="4ad03-111">Le condizioni seguenti possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="4ad03-111">The following conditions may cause an exception to be thrown:</span></span>  
  
-   <span data-ttu-id="4ad03-112">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4ad03-113">Il sistema non ha recuperato il percorso assoluto (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-113">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4ad03-114">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4ad03-115">Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-115">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="4ad03-116">Il percorso combinato punta a una directory esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-116">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4ad03-117">Il file di destinazione esiste e `overwrite` è impostato su `False` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-117">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4ad03-118">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-118">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4ad03-119">Un file nella cartella di destinazione con lo stesso nome è in uso (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-119">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4ad03-120">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-120">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4ad03-121">`ShowUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e l'utente ha annullato l'operazione (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-121">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="4ad03-122">`ShowUI`è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e si verifica un errore di I/O non specificato (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-122">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="4ad03-123">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-123">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="4ad03-124">L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-124">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="4ad03-125">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="4ad03-125">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad03-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad03-126">See Also</span></span>  
 <span data-ttu-id="4ad03-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="4ad03-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="4ad03-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span><span class="sxs-lookup"><span data-stu-id="4ad03-128"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A></span></span>   
 <span data-ttu-id="4ad03-129"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span><span class="sxs-lookup"><span data-stu-id="4ad03-129"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span></span>   
 <span data-ttu-id="4ad03-130">[Procedura: Copiare file con un criterio specifico in una directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md) </span><span class="sxs-lookup"><span data-stu-id="4ad03-130">[How to: Copy Files with a Specific Pattern to a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md) </span></span>  
 <span data-ttu-id="4ad03-131">[Procedura: Creare una copia di un file nella stessa directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md) </span><span class="sxs-lookup"><span data-stu-id="4ad03-131">[How to: Create a Copy of a File in the Same Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md) </span></span>  
 <span data-ttu-id="4ad03-132">[Procedura: Copiare una directory in un'altra directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md) </span><span class="sxs-lookup"><span data-stu-id="4ad03-132">[How to: Copy a Directory to Another Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md) </span></span>  
 [<span data-ttu-id="4ad03-133">Procedura: rinominare un file</span><span class="sxs-lookup"><span data-stu-id="4ad03-133">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)

