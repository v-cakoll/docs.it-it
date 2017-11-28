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
# <a name="unable-to-obtain-a-stream-for-the-log"></a>Impossibile ottenere un flusso per il log
Impossibile ottenere un flusso per il log. Nomi potenziali dei file in base a \<nome > sono già in uso.  
  
 Il <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> classe non può creare un nuovo file di log, perché tutti i possibili nomi di file di log basano su \<nome > sono già in uso.  
  
 L'esistenza di un numero eccessivo di file di log può indicare un problema architetturale dell'applicazione. Per altre informazioni, vedere la documentazione per la classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> su <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> o <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> per includere nel nome del file di log un indicatore di data.  
  
2.  Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [Oggetto My.Application.Log](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [Oggetto My.Log](../../visual-basic/language-reference/objects/my-log-object.md)
