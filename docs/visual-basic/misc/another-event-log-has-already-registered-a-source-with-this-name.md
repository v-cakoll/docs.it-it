---
title: "Un altro log eventi ha già registrato un'origine con questo nome"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="17237-102">Un altro log eventi ha già registrato un'origine con questo nome</span><span class="sxs-lookup"><span data-stu-id="17237-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="17237-103">Si è provato a scrivere una voce in un log eventi ma l'origine specificata è stata registrata in un altro log eventi.</span><span class="sxs-lookup"><span data-stu-id="17237-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="17237-104">Per consentire al componente <xref:System.Diagnostics.EventLog.Source%2A> di scrivere voci in un log, è necessario impostare la proprietà <xref:System.Diagnostics.EventLog> sull'istanza del componente.</span><span class="sxs-lookup"><span data-stu-id="17237-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="17237-105">Quando si esegue questa operazione, viene controllato che l'origine specificata sia registrata nel log eventi in cui viene scritto il componente e, se necessario, viene chiamata la proprietà <xref:System.Diagnostics.EventLog.CreateEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="17237-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="17237-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="17237-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="17237-107">Rimuovere l'associazione tra l'origine e il primo log usando il metodo <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="17237-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="17237-108">Registrare l'origine nel nuovo log.</span><span class="sxs-lookup"><span data-stu-id="17237-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17237-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17237-109">See Also</span></span>  
 [<span data-ttu-id="17237-110">Oggetto My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="17237-110">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="17237-111">Procedura: rimuovere un'origine evento</span><span class="sxs-lookup"><span data-stu-id="17237-111">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [<span data-ttu-id="17237-112">Procedura: aggiungere l'applicazione come origine delle voci del registro eventi</span><span class="sxs-lookup"><span data-stu-id="17237-112">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
