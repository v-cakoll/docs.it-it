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
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="3a120-102">Errore durante la gestione delle attività asincrone</span><span class="sxs-lookup"><span data-stu-id="3a120-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="3a120-103">Fornire la gestione degli errori in <xref:System.Activities.AsyncCodeActivity> implica risolvere gli errori tramite il sistema di callback dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3a120-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="3a120-104">In questo argomento viene descritto come restituire un errore generato in un'unica operazione asincrona all'host, usando come esempio l'attività SendMail.</span><span class="sxs-lookup"><span data-stu-id="3a120-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="3a120-105">Restituisce un errore generato in un'attività asincrona all'host</span><span class="sxs-lookup"><span data-stu-id="3a120-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="3a120-106">La restituzione all'host di un errore in un'operazione asincrona nell'esempio di attività SendMail include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a120-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
-   <span data-ttu-id="3a120-107">Aggiungere una proprietà Exception alla classe `SendMailAsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="3a120-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
-   <span data-ttu-id="3a120-108">Copiare l'errore generato a tale proprietà nel gestore eventi `SendCompleted`.</span><span class="sxs-lookup"><span data-stu-id="3a120-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
-   <span data-ttu-id="3a120-109">Generare l'eccezione nel gestore eventi `EndExecute`.</span><span class="sxs-lookup"><span data-stu-id="3a120-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="3a120-110">Di seguito è riportato il codice risultante.</span><span class="sxs-lookup"><span data-stu-id="3a120-110">The resulting code is as follows.</span></span>  
  
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
