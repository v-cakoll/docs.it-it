---
title: Impossibile ottenere un flusso per il log
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 45b7a16608bea4879e84fa7004097a8c38312284
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58031702"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="9a86e-102">Impossibile ottenere un flusso per il log</span><span class="sxs-lookup"><span data-stu-id="9a86e-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="9a86e-103">Impossibile ottenere un flusso per il log.</span><span class="sxs-lookup"><span data-stu-id="9a86e-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="9a86e-104">I possibili nome file basati \<nome > sono già in uso.</span><span class="sxs-lookup"><span data-stu-id="9a86e-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="9a86e-105">Il <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> classe non è stato possibile creare un nuovo file di log perché tutti i possibili nomi di file di log basano su \<nome > sono già in uso.</span><span class="sxs-lookup"><span data-stu-id="9a86e-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="9a86e-106">L'esistenza di un numero eccessivo di file di log può indicare un problema architetturale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a86e-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="9a86e-107">Per altre informazioni, vedere la documentazione per la classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="9a86e-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9a86e-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9a86e-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="9a86e-109">Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> su <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> per includere nel nome del file di log un indicatore di data.</span><span class="sxs-lookup"><span data-stu-id="9a86e-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="9a86e-110">Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.</span><span class="sxs-lookup"><span data-stu-id="9a86e-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a86e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a86e-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="9a86e-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="9a86e-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="9a86e-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="9a86e-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
