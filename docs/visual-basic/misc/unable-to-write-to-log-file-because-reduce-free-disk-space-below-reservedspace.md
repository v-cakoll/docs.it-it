---
title: Impossibile scrivere nel file di log. Lo spazio libero su disco risulterebbe inferiore al valore ReservedSpace
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 486f27efe5da0a5d663e7bdae9d5789df4add4e7
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a><span data-ttu-id="cc1d8-102">Impossibile scrivere nel file di log. Lo spazio libero su disco risulterebbe inferiore al valore ReservedSpace</span><span class="sxs-lookup"><span data-stu-id="cc1d8-102">Unable to write to log file because writing to it would reduce free disk space below ReservedSpace value</span></span>
<span data-ttu-id="cc1d8-103">La classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> non è riuscita a scrivere nel file di log perché:</span><span class="sxs-lookup"><span data-stu-id="cc1d8-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="cc1d8-104">La quantità di spazio disponibile su disco (in byte) è minore del valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> </span><span class="sxs-lookup"><span data-stu-id="cc1d8-104">The amount of free disk space (in bytes) is less than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property</span></span>  
  
     <span data-ttu-id="cc1d8-105">e</span><span class="sxs-lookup"><span data-stu-id="cc1d8-105">—and—</span></span>  
  
-   <span data-ttu-id="cc1d8-106">Il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> è <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="cc1d8-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc1d8-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="cc1d8-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="cc1d8-108">Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.</span><span class="sxs-lookup"><span data-stu-id="cc1d8-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2.  <span data-ttu-id="cc1d8-109">Modificare il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> impostando un numero inferiore per riservare meno spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="cc1d8-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property to a smaller number to reserve less disk space.</span></span>  
  
3.  <span data-ttu-id="cc1d8-110">Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> su <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> per eliminare i messaggi senza avviso se lo spazio disponibile su disco è insufficiente.</span><span class="sxs-lookup"><span data-stu-id="cc1d8-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if there is not enough free disk space.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc1d8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc1d8-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [<span data-ttu-id="cc1d8-112">My</span><span class="sxs-lookup"><span data-stu-id="cc1d8-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="cc1d8-113">DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="cc1d8-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
