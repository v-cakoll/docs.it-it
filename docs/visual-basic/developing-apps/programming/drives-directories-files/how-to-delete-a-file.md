---
title: 'Procedura: eliminare un file in Visual Basic'
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
- Delete method
- files, deleting
- files, manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
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
ms.openlocfilehash: e4b0b87fd403556777e0ab5a1edd517687360374
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="838bd-102">Procedura: eliminare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="838bd-102">How to: Delete a File in Visual Basic</span></span>
<span data-ttu-id="838bd-103">Il metodo `DeleteFile` dell'oggetto `My.Computer.FileSystem` consente l'eliminazione di un file.</span><span class="sxs-lookup"><span data-stu-id="838bd-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="838bd-104">È possibile scegliere di inviare il file eliminato al **Cestino**, chiedere all'utente di confermare l'eliminazione del file e decidere cosa fare quando l'utente annulla l'operazione.</span><span class="sxs-lookup"><span data-stu-id="838bd-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="838bd-105">Per eliminare un file di testo</span><span class="sxs-lookup"><span data-stu-id="838bd-105">To delete a text file</span></span>  
  
-   <span data-ttu-id="838bd-106">Usare il metodo `DeleteFile` per eliminare il file.</span><span class="sxs-lookup"><span data-stu-id="838bd-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="838bd-107">Il codice seguente illustra come eliminare il file denominato `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="838bd-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     <span data-ttu-id="838bd-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="838bd-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="838bd-109">Per eliminare un file di testo e chiedere all'utente di confermare l'eliminazione del file</span><span class="sxs-lookup"><span data-stu-id="838bd-109">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
-   <span data-ttu-id="838bd-110">Usare il metodo `DeleteFile` per eliminare il file, impostando `showUI` su `AllDialogs`.</span><span class="sxs-lookup"><span data-stu-id="838bd-110">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="838bd-111">Il codice seguente illustra come eliminare il file denominato `test.txt` e consentire all'utente di confermare l'eliminazione del file.</span><span class="sxs-lookup"><span data-stu-id="838bd-111">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     <span data-ttu-id="838bd-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="838bd-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="838bd-113">Per eliminare un file di testo e inviarlo al Cestino</span><span class="sxs-lookup"><span data-stu-id="838bd-113">To delete a text file and send it to the Recycle Bin</span></span>  
  
-   <span data-ttu-id="838bd-114">Usare il metodo `DeleteFile` per eliminare il file, specificando `SendToRecycleBin` per il parametro `recycle`.</span><span class="sxs-lookup"><span data-stu-id="838bd-114">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="838bd-115">Il codice seguente illustra come eliminare il file denominato `test.txt` e inviarlo al **Cestino**.</span><span class="sxs-lookup"><span data-stu-id="838bd-115">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     <span data-ttu-id="838bd-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="838bd-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="838bd-117">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="838bd-117">Robust Programming</span></span>  
 <span data-ttu-id="838bd-118">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="838bd-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="838bd-119">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="838bd-120">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="838bd-121">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="838bd-122">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-122">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="838bd-123">Il file è in uso (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-123">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="838bd-124">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="838bd-125">Il file non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-125">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="838bd-126">L'utente non è autorizzato a eliminare il file oppure il file è di sola lettura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-126">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="838bd-127">Esiste un contesto di attendibilità parziale in cui l'utente non ha autorizzazioni sufficienti (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-127">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="838bd-128">L'utente ha annullato l'operazione e `onUserCancel` è impostato su `ThrowException` (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="838bd-128">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="838bd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="838bd-129">See Also</span></span>  
 <span data-ttu-id="838bd-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span><span class="sxs-lookup"><span data-stu-id="838bd-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span></span>   
 <span data-ttu-id="838bd-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="838bd-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="838bd-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span><span class="sxs-lookup"><span data-stu-id="838bd-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span></span>   
 <span data-ttu-id="838bd-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span><span class="sxs-lookup"><span data-stu-id="838bd-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span></span>   
 [<span data-ttu-id="838bd-134">Procedura: ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="838bd-134">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

