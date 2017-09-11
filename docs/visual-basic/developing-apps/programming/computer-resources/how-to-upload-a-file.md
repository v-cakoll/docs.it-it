---
title: 'Procedura: caricare un file in Visual Basic'
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
- networks, uploading files
- files, uploading
- uploading files
- UploadFile method
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
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
ms.openlocfilehash: 29baf1f420cece6e0b05f9638b30a326178a013d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="b5670-102">Procedura: caricare un file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5670-102">How to: Upload a File in Visual Basic</span></span>
<span data-ttu-id="b5670-103">Il metodo <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> consente di caricare un file e archiviarlo in un percorso remoto.</span><span class="sxs-lookup"><span data-stu-id="b5670-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="b5670-104">Se il parametro `ShowUI` è impostato su `True`, viene visualizzata una finestra di dialogo che mostra lo stato di avanzamento del processo di caricamento e consente agli utenti di annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b5670-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="b5670-105">Per caricare un file</span><span class="sxs-lookup"><span data-stu-id="b5670-105">To upload a file</span></span>  
  
-   <span data-ttu-id="b5670-106">Usare il metodo `UploadFile` per caricare un file, specificando il percorso del file di origine e il percorso della directory di destinazione come stringa o URI (Uniform Resource Identifier). Nell'esempio riportato di seguito il file `Order.txt` viene caricato in `http://www.cohowinery.com/uploads.aspx`.</span><span class="sxs-lookup"><span data-stu-id="b5670-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     <span data-ttu-id="b5670-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5670-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span></span>  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="b5670-108">Per caricare un file e visualizzare lo stato di avanzamento dell'operazione</span><span class="sxs-lookup"><span data-stu-id="b5670-108">To upload a file and show the progress of the operation</span></span>  
  
-   <span data-ttu-id="b5670-109">Usare il metodo `UploadFile` per caricare un file, specificando il percorso del file di origine e il percorso della directory di destinazione come stringa o URI.</span><span class="sxs-lookup"><span data-stu-id="b5670-109">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="b5670-110">Nell'esempio riportato di seguito il file `Order.txt` viene caricato in `http://www.cohowinery.com/uploads.aspx` senza specificare un nome utente o una password, viene visualizzato lo stato di avanzamento del processo di caricamento ed è previsto un intervallo di timeout di 500 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="b5670-110">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     <span data-ttu-id="b5670-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5670-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span></span>  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="b5670-112">Per caricare un file, specificando un nome utente e una password</span><span class="sxs-lookup"><span data-stu-id="b5670-112">To upload a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="b5670-113">Usare il metodo `UploadFile` per caricare un file, specificando il percorso del file di origine e il percorso della directory di destinazione come stringa o URI e indicando il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="b5670-113">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="b5670-114">Nell'esempio riportato di seguito il file `Order.txt` viene caricato in `http://www.cohowinery.com/uploads.aspx` specificando il nome utente `anonymous` e una password vuota.</span><span class="sxs-lookup"><span data-stu-id="b5670-114">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     <span data-ttu-id="b5670-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5670-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b5670-116">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="b5670-116">Robust Programming</span></span>  
 <span data-ttu-id="b5670-117">Le condizioni seguenti possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="b5670-117">The following conditions may throw an exception:</span></span>  
  
-   <span data-ttu-id="b5670-118">Il percorso file locale non è valido (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b5670-118">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="b5670-119">Autenticazione non riuscita (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b5670-119">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="b5670-120">Timeout della connessione (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="b5670-120">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5670-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5670-121">See Also</span></span>  
 <span data-ttu-id="b5670-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b5670-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span></span>   
 <span data-ttu-id="b5670-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span><span class="sxs-lookup"><span data-stu-id="b5670-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span></span>   
 <span data-ttu-id="b5670-124">[Procedura: Scaricare file](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="b5670-124">[How to: Download a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span></span>  
 [<span data-ttu-id="b5670-125">Procedura: analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="b5670-125">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

