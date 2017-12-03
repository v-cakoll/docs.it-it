---
title: "Errore durante la gestione delle attività asincrone"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7c23dec2f92ed8654d5f0460966dc19af0a8405
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="error-handling-in-asynchronous-activities"></a>Errore durante la gestione delle attività asincrone
Fornire la gestione degli errori in <xref:System.Activities.AsyncCodeActivity> implica risolvere gli errori tramite il sistema di callback dell'attività. In questo argomento viene descritto come restituire un errore generato in un'unica operazione asincrona all'host, usando come esempio l'attività SendMail.  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>Restituisce un errore generato in un'attività asincrona all'host  
 La restituzione all'host di un errore in un'operazione asincrona nell'esempio di attività SendMail include i passaggi seguenti:  
  
-   Aggiungere una proprietà Exception alla classe `SendMailAsyncResult`.  
  
-   Copiare l'errore generato a tale proprietà nel gestore eventi `SendCompleted`.  
  
-   Generare l'eccezione nel gestore eventi `EndExecute`.  
  
 Di seguito è riportato il codice risultante.  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }   
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;   
        }  
    }  
```
