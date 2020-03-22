---
title: 'Procedura: scaricare file'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: 4923feb46ff638de9514a4d70fc00367491a6f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345626"
---
# <a name="how-to-download-a-file-in-visual-basic"></a><span data-ttu-id="64b53-102">Procedura: scaricare file in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="64b53-102">How to: Download a File in Visual Basic</span></span>

<span data-ttu-id="64b53-103">Il metodo <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> può essere usato per scaricare un file remoto e archiviarlo in un percorso specifico.</span><span class="sxs-lookup"><span data-stu-id="64b53-103">The <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> method can be used to download a remote file and store it to a specific location.</span></span> <span data-ttu-id="64b53-104">Se il parametro `ShowUI` è impostato su `True`, viene visualizzata una finestra che mostra lo stato di avanzamento del download e consente agli utenti di annullare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="64b53-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed showing the progress of the download and allowing users to cancel the operation.</span></span> <span data-ttu-id="64b53-105">Per impostazione predefinita non vengono sovrascritti i file esistenti con lo stesso nome. Se si desidera sovrascrivere i file esistenti, impostare il parametro `overwrite` su `True`.</span><span class="sxs-lookup"><span data-stu-id="64b53-105">By default, existing files having the same name are not overwritten; if you want to overwrite existing files, set the `overwrite` parameter to `True`.</span></span>

<span data-ttu-id="64b53-106">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="64b53-106">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="64b53-107">Il nome dell'unità non è valido (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="64b53-107">Drive name is not valid (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="64b53-108">L'autenticazione necessaria non è stata fornita (<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="64b53-108">Necessary authentication has not been supplied (<xref:System.UnauthorizedAccessException> or <xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="64b53-109">Il server non risponde entro il `connectionTimeout` (<xref:System.TimeoutException>) specificato.</span><span class="sxs-lookup"><span data-stu-id="64b53-109">The server does not respond within the specified `connectionTimeout` (<xref:System.TimeoutException>).</span></span>

- <span data-ttu-id="64b53-110">La richiesta è stata rifiutata dal sito Web (<xref:System.Net.WebException>).</span><span class="sxs-lookup"><span data-stu-id="64b53-110">The request is denied by the Web site (<xref:System.Net.WebException>).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> <span data-ttu-id="64b53-111">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="64b53-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="64b53-112">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="64b53-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="64b53-113">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="64b53-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="64b53-114">È possibile che il contenuto del file non corrisponda a quanto previsto e che quindi i metodi per la lettura dal file non abbiano esito positivo.</span><span class="sxs-lookup"><span data-stu-id="64b53-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

### <a name="to-download-a-file"></a><span data-ttu-id="64b53-115">Per scaricare un file</span><span class="sxs-lookup"><span data-stu-id="64b53-115">To download a file</span></span>

- <span data-ttu-id="64b53-116">Usare il metodo `DownloadFile` per scaricare il file, specificando il percorso del file di destinazione come stringa o URI e specificando la posizione in cui archiviare il file.</span><span class="sxs-lookup"><span data-stu-id="64b53-116">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file.</span></span> <span data-ttu-id="64b53-117">Questo esempio scarica il file `WineList.txt` da `http://www.cohowinery.com/downloads` e lo salva in `C:\Documents and Settings\All Users\Documents`:</span><span class="sxs-lookup"><span data-stu-id="64b53-117">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`:</span></span>

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a><span data-ttu-id="64b53-118">Per scaricare un file, specificando un intervallo di timeout</span><span class="sxs-lookup"><span data-stu-id="64b53-118">To download a file, specifying a time-out interval</span></span>

- <span data-ttu-id="64b53-119">Usare il metodo `DownloadFile` per scaricare il file, specificando il percorso del file di destinazione come stringa o URI che specifica la posizione in cui archiviare il file e specificando l'intervallo di timeout in millisecondi (il valore predefinito è 1000).</span><span class="sxs-lookup"><span data-stu-id="64b53-119">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI, specifying the location at which to store the file, and specifying the time-out interval in milliseconds (the default is 1000).</span></span> <span data-ttu-id="64b53-120">Questo esempio scarica il file `WineList.txt` da `http://www.cohowinery.com/downloads` e lo salva in `C:\Documents and Settings\All Users\Documents`, specificando un intervallo di timeout di 500 millisecondi:</span><span class="sxs-lookup"><span data-stu-id="64b53-120">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, specifying a time-out interval of 500 milliseconds:</span></span>

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="64b53-121">Per scaricare un file, fornendo un nome utente e una password</span><span class="sxs-lookup"><span data-stu-id="64b53-121">To download a file, supplying a user name and password</span></span>

- <span data-ttu-id="64b53-122">Usare il metodo `DownLoadFile` per scaricare il file, specificando il percorso del file di destinazione come stringa o URI e specificando la posizione in cui archiviare il file, il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="64b53-122">Use the `DownLoadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file, the user name, and the password.</span></span> <span data-ttu-id="64b53-123">Questo esempio scarica il file `WineList.txt` da `http://www.cohowinery.com/downloads` e lo salva in `C:\Documents and Settings\All Users\Documents`, con il nome utente `anonymous` e una password vuota.</span><span class="sxs-lookup"><span data-stu-id="64b53-123">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, with the user name `anonymous` and a blank password.</span></span>

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > <span data-ttu-id="64b53-124">Il protocollo FTP utilizzato dal metodo `DownLoadFile` invia informazioni, comprese le password, in testo normale e non deve essere usato per trasmettere informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="64b53-124">The FTP protocol used by the `DownLoadFile` method sends information, including passwords, in plain text and should not be used for transmitting sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="64b53-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64b53-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [<span data-ttu-id="64b53-126">Procedura: caricare un fileHow to: Upload a File</span><span class="sxs-lookup"><span data-stu-id="64b53-126">How to: Upload a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)
- [<span data-ttu-id="64b53-127">Procedura: analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="64b53-127">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
