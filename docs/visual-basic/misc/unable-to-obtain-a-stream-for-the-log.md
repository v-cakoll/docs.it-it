---
title: Impossibile ottenere un flusso per il log
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd3051b2331502c9f4f3430bbf88731b307d1b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="786de-102">Impossibile ottenere un flusso per il log</span><span class="sxs-lookup"><span data-stu-id="786de-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="786de-103">Impossibile ottenere un flusso per il log.</span><span class="sxs-lookup"><span data-stu-id="786de-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="786de-104">Nomi potenziali dei file in base a \<nome > sono già in uso.</span><span class="sxs-lookup"><span data-stu-id="786de-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="786de-105">Il <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> classe non può creare un nuovo file di log, perché tutti i possibili nomi di file di log basano su \<nome > sono già in uso.</span><span class="sxs-lookup"><span data-stu-id="786de-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="786de-106">L'esistenza di un numero eccessivo di file di log può indicare un problema architetturale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="786de-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="786de-107">Per altre informazioni, vedere la documentazione per la classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="786de-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="786de-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="786de-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="786de-109">Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> su <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> per includere nel nome del file di log un indicatore di data.</span><span class="sxs-lookup"><span data-stu-id="786de-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="786de-110">Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.</span><span class="sxs-lookup"><span data-stu-id="786de-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786de-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="786de-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [<span data-ttu-id="786de-112">Oggetto My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="786de-112">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="786de-113">Oggetto My.Log</span><span class="sxs-lookup"><span data-stu-id="786de-113">My.Log Object</span></span>](../../visual-basic/language-reference/objects/my-log-object.md)
