---
title: 'Procedura: creare una copia di un file nella stessa directory'
ms.date: 07/20/2015
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
ms.openlocfilehash: 33a4f5424ac50de7b5dc988034ca15127dc1ed02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348827"
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a><span data-ttu-id="0c34e-102">Procedura: creare una copia di un file nella stessa directory in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c34e-102">How to: Create a Copy of a File in the Same Directory in Visual Basic</span></span>

<span data-ttu-id="0c34e-103">Usare il metodo `My.Computer.FileSystem.CopyFile` per copiare i file.</span><span class="sxs-lookup"><span data-stu-id="0c34e-103">Use the `My.Computer.FileSystem.CopyFile` method to copy files.</span></span> <span data-ttu-id="0c34e-104">I parametri consentono di sovrascrivere file esistenti, rinominare il file, visualizzare lo stato di avanzamento dell'operazione e permettere all'utente di annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="0c34e-104">The parameters allow you to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a><span data-ttu-id="0c34e-105">Per creare una copia di un file nella stessa directory</span><span class="sxs-lookup"><span data-stu-id="0c34e-105">To create a copy of a file in the same folder</span></span>  
  
- <span data-ttu-id="0c34e-106">Usare il metodo `CopyFile` specificando il percorso e il file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0c34e-106">Use the `CopyFile` method, supplying the target file and the location.</span></span> <span data-ttu-id="0c34e-107">Nell'esempio seguente viene creata una copia di `test2.txt` denominata `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="0c34e-107">The following example creates a copy of `test.txt` called `test2.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#51)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a><span data-ttu-id="0c34e-108">Per creare una copia di un file nella stessa cartella, sovrascrivendo i file esistenti</span><span class="sxs-lookup"><span data-stu-id="0c34e-108">To create a copy of a file in the same folder, overwriting existing files</span></span>  
  
- <span data-ttu-id="0c34e-109">Usare il metodo `CopyFile` specificando il percorso e il file di destinazione e impostando `overwrite` su `True`.</span><span class="sxs-lookup"><span data-stu-id="0c34e-109">Use the `CopyFile` method, supplying the target file and location, and setting `overwrite` to `True`.</span></span> <span data-ttu-id="0c34e-110">Nell'esempio riportato di seguito viene creata una copia di `test.txt` denominata `test2.txt` e i file esistenti vengono sovrascritti con questo nome.</span><span class="sxs-lookup"><span data-stu-id="0c34e-110">The following example creates a copy of `test.txt` called `test2.txt` and overwrites any existing files by that name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#52)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0c34e-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="0c34e-111">Robust Programming</span></span>  

 <span data-ttu-id="0c34e-112">Le condizioni seguenti possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="0c34e-112">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="0c34e-113">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="0c34e-114">Il sistema non ha recuperato il percorso assoluto (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-114">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="0c34e-115">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="0c34e-116">Il file di origine non è valido o non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-116">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="0c34e-117">Il percorso combinato punta a una directory esistente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-117">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="0c34e-118">Il file di destinazione esiste e `overwrite` è impostato su `False` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-118">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="0c34e-119">L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-119">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="0c34e-120">Un file nella cartella di destinazione con lo stesso nome è in uso (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-120">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="0c34e-121">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-121">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="0c34e-122">`ShowUI` è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e l'utente ha annullato l'operazione (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-122">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="0c34e-123">`ShowUI`è impostato su `True`, `onUserCancel` è impostato su `ThrowException` e si verifica un errore di I/O non specificato (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-123">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="0c34e-124">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-124">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="0c34e-125">L'utente non ha le autorizzazioni necessarie (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-125">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="0c34e-126">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="0c34e-126">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c34e-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0c34e-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="0c34e-128">Procedura: copiare file con un criterio specifico in una directory</span><span class="sxs-lookup"><span data-stu-id="0c34e-128">How to: Copy Files with a Specific Pattern to a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="0c34e-129">Procedura: creare una copia di un file in una directory diversa</span><span class="sxs-lookup"><span data-stu-id="0c34e-129">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [<span data-ttu-id="0c34e-130">Procedura: copiare una directory in un'altra directory</span><span class="sxs-lookup"><span data-stu-id="0c34e-130">How to: Copy a Directory to Another Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="0c34e-131">Procedura: rinominare un file</span><span class="sxs-lookup"><span data-stu-id="0c34e-131">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
