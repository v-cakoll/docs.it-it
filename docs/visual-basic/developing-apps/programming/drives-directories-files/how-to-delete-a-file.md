---
title: 'Procedura: eliminare un file'
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 57182f1a1d92b7fe954fd26b32c5e4b1107823ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348785"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="f1697-102">Procedura: eliminare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1697-102">How to: Delete a File in Visual Basic</span></span>

<span data-ttu-id="f1697-103">Il metodo `DeleteFile` dell'oggetto `My.Computer.FileSystem` consente l'eliminazione di un file.</span><span class="sxs-lookup"><span data-stu-id="f1697-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="f1697-104">È possibile scegliere di inviare il file eliminato al **Cestino**, chiedere all'utente di confermare l'eliminazione del file e decidere cosa fare quando l'utente annulla l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f1697-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="f1697-105">Per eliminare un file di testo</span><span class="sxs-lookup"><span data-stu-id="f1697-105">To delete a text file</span></span>  
  
- <span data-ttu-id="f1697-106">Usare il metodo `DeleteFile` per eliminare il file.</span><span class="sxs-lookup"><span data-stu-id="f1697-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="f1697-107">Il codice seguente illustra come eliminare il file denominato `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="f1697-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="f1697-108">Per eliminare un file di testo e chiedere all'utente di confermare l'eliminazione del file</span><span class="sxs-lookup"><span data-stu-id="f1697-108">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
- <span data-ttu-id="f1697-109">Usare il metodo `DeleteFile` per eliminare il file, impostando `showUI` su `AllDialogs`.</span><span class="sxs-lookup"><span data-stu-id="f1697-109">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="f1697-110">Il codice seguente illustra come eliminare il file denominato `test.txt` e consentire all'utente di confermare l'eliminazione del file.</span><span class="sxs-lookup"><span data-stu-id="f1697-110">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="f1697-111">Per eliminare un file di testo e inviarlo al Cestino</span><span class="sxs-lookup"><span data-stu-id="f1697-111">To delete a text file and send it to the Recycle Bin</span></span>  
  
- <span data-ttu-id="f1697-112">Usare il metodo `DeleteFile` per eliminare il file, specificando `SendToRecycleBin` per il parametro `recycle`.</span><span class="sxs-lookup"><span data-stu-id="f1697-112">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="f1697-113">Il codice seguente illustra come eliminare il file denominato `test.txt` e inviarlo al **Cestino**.</span><span class="sxs-lookup"><span data-stu-id="f1697-113">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f1697-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f1697-114">Robust Programming</span></span>  

 <span data-ttu-id="f1697-115">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="f1697-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="f1697-116">Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-116">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="f1697-117">Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="f1697-118">La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="f1697-119">Il nome di un file o di una cartella nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="f1697-120">Il file è in uso (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-120">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="f1697-121">L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="f1697-122">Il file non esiste (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-122">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="f1697-123">L'utente non è autorizzato a eliminare il file oppure il file è di sola lettura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-123">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="f1697-124">Esiste un contesto di attendibilità parziale in cui l'utente non ha autorizzazioni sufficienti (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-124">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="f1697-125">L'utente ha annullato l'operazione e `onUserCancel` è impostato su `ThrowException` (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="f1697-125">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1697-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1697-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [<span data-ttu-id="f1697-127">Procedura: ottenere la raccolta di file di una directory</span><span class="sxs-lookup"><span data-stu-id="f1697-127">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
