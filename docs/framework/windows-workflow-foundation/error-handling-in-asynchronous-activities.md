---
title: Errore durante la gestione delle attività asincrone
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: 4a7cbecef596eec6eaa128b8ffc7bc5c6e4b79bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511982"
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="cdb5a-102">Errore durante la gestione delle attività asincrone</span><span class="sxs-lookup"><span data-stu-id="cdb5a-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="cdb5a-103">Fornire la gestione degli errori in <xref:System.Activities.AsyncCodeActivity> implica risolvere gli errori tramite il sistema di callback dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cdb5a-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="cdb5a-104">In questo argomento viene descritto come restituire un errore generato in un'unica operazione asincrona all'host, usando come esempio l'attività SendMail.</span><span class="sxs-lookup"><span data-stu-id="cdb5a-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="cdb5a-105">Restituisce un errore generato in un'attività asincrona all'host</span><span class="sxs-lookup"><span data-stu-id="cdb5a-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="cdb5a-106">La restituzione all'host di un errore in un'operazione asincrona nell'esempio di attività SendMail include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdb5a-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
-   <span data-ttu-id="cdb5a-107">Aggiungere una proprietà Exception alla classe `SendMailAsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="cdb5a-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
-   <span data-ttu-id="cdb5a-108">Copiare l'errore generato a tale proprietà nel gestore eventi `SendCompleted`.</span><span class="sxs-lookup"><span data-stu-id="cdb5a-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
-   <span data-ttu-id="cdb5a-109">Generare l'eccezione nel gestore eventi `EndExecute`.</span><span class="sxs-lookup"><span data-stu-id="cdb5a-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="cdb5a-110">Di seguito è riportato il codice risultante.</span><span class="sxs-lookup"><span data-stu-id="cdb5a-110">The resulting code is as follows.</span></span>  
  
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
