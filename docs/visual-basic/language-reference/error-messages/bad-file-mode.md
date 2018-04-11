---
title: Modalità file non valida
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a><span data-ttu-id="5a5aa-102">Modalità file non valida</span><span class="sxs-lookup"><span data-stu-id="5a5aa-102">Bad file mode</span></span>
<span data-ttu-id="5a5aa-103">Le istruzioni utilizzate nella modifica dei contenuti del file devono essere appropriate per la modalità in cui è stato aperto il file.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="5a5aa-104">Fra le cause possibili vi sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a5aa-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="5a5aa-105">Oggetto `FilePutObject` o `FileGetObject` istruzione specifica un file sequenziale.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="5a5aa-106">Oggetto `Print` istruzione specifica un file aperto in modalità di accesso diverso da `Output` o `Append`.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="5a5aa-107">Un `Input` istruzione specifica un file aperto in modalità di accesso diverso da`Input`</span><span class="sxs-lookup"><span data-stu-id="5a5aa-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="5a5aa-108">Tentativo di scrivere in un file di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a5aa-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5a5aa-109">To correct this error</span></span>  
  
-   <span data-ttu-id="5a5aa-110">Assicurarsi che `FilePutObject` e `FileGetObject` facciano riferimento solo a file aperti per `Random` o `Binary` accesso.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="5a5aa-111">Assicurarsi che `Print` specifica un file aperto per la `Output` o `Append` modalità di accesso.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="5a5aa-112">In caso contrario, utilizzare un'istruzione diversa per inserire dati nel file o riaprire il file in una modalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="5a5aa-113">Assicurarsi che `Input` specifica un file aperto per `Input`.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="5a5aa-114">In caso contrario, utilizzare un'istruzione diversa per inserire dati nel file o riaprire il file in una modalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="5a5aa-115">Se si scrive in un file di sola lettura, modificare lo stato di lettura/scrittura del file o non tentare di scrivervi.</span><span class="sxs-lookup"><span data-stu-id="5a5aa-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="5a5aa-116">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="5a5aa-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5aa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a5aa-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [<span data-ttu-id="5a5aa-118">Risoluzione dei problemi: lettura e scrittura nei file di testo</span><span class="sxs-lookup"><span data-stu-id="5a5aa-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
