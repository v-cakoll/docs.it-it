---
title: Impossibile ottenere un flusso per il log
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 3f5ac83e6957d6d5883bf5ab191e2a922c874df3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33639533"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="2bf81-102">Impossibile ottenere un flusso per il log</span><span class="sxs-lookup"><span data-stu-id="2bf81-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="2bf81-103">Impossibile ottenere un flusso per il log.</span><span class="sxs-lookup"><span data-stu-id="2bf81-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="2bf81-104">Nomi potenziali dei file in base a \<nome > sono già in uso.</span><span class="sxs-lookup"><span data-stu-id="2bf81-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="2bf81-105">Il <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> classe non può creare un nuovo file di log, perché tutti i possibili nomi di file di log basano su \<nome > sono già in uso.</span><span class="sxs-lookup"><span data-stu-id="2bf81-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="2bf81-106">L'esistenza di un numero eccessivo di file di log può indicare un problema architetturale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2bf81-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="2bf81-107">Per altre informazioni, vedere la documentazione per la classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="2bf81-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2bf81-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2bf81-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="2bf81-109">Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> su <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> per includere nel nome del file di log un indicatore di data.</span><span class="sxs-lookup"><span data-stu-id="2bf81-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="2bf81-110">Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.</span><span class="sxs-lookup"><span data-stu-id="2bf81-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf81-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bf81-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [<span data-ttu-id="2bf81-112">My</span><span class="sxs-lookup"><span data-stu-id="2bf81-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="2bf81-113">DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="2bf81-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
