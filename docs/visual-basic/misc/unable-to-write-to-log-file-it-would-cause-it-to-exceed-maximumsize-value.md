---
title: Impossibile scrivere nel file di log. Verrebbe superato il valore MaximumSize
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4004dca2a3b9f13583cfdfe43f89bc4bff5dd6d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="e3d7a-102">Impossibile scrivere nel file di log. Verrebbe superato il valore MaximumSize</span><span class="sxs-lookup"><span data-stu-id="e3d7a-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>
<span data-ttu-id="e3d7a-103">La classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> non è riuscita a scrivere nel file di log perché:</span><span class="sxs-lookup"><span data-stu-id="e3d7a-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="e3d7a-104">La dimensione del file di log (in byte) è maggiore rispetto al valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> </span><span class="sxs-lookup"><span data-stu-id="e3d7a-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="e3d7a-105">e</span><span class="sxs-lookup"><span data-stu-id="e3d7a-105">—and—</span></span>  
  
-   <span data-ttu-id="e3d7a-106">Il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> è <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3d7a-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e3d7a-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="e3d7a-108">Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2.  <span data-ttu-id="e3d7a-109">Modificare il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> per consentire log di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3.  <span data-ttu-id="e3d7a-110">Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> su <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> per eliminare i messaggi senza avviso se il log è troppo grande.</span><span class="sxs-lookup"><span data-stu-id="e3d7a-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d7a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3d7a-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [<span data-ttu-id="e3d7a-112">My</span><span class="sxs-lookup"><span data-stu-id="e3d7a-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="e3d7a-113">DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="e3d7a-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
