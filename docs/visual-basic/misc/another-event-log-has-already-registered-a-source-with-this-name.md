---
title: Un altro log eventi ha già registrato un'origine con questo nome
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: d932869504b2d8a5f3a948b190e5528bfcfa664f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314672"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="b0ce6-102">Un altro log eventi ha già registrato un'origine con questo nome</span><span class="sxs-lookup"><span data-stu-id="b0ce6-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="b0ce6-103">Si è provato a scrivere una voce in un log eventi ma l'origine specificata è stata registrata in un altro log eventi.</span><span class="sxs-lookup"><span data-stu-id="b0ce6-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="b0ce6-104">Per consentire al componente <xref:System.Diagnostics.EventLog.Source%2A> di scrivere voci in un log, è necessario impostare la proprietà <xref:System.Diagnostics.EventLog> sull'istanza del componente.</span><span class="sxs-lookup"><span data-stu-id="b0ce6-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="b0ce6-105">Quando si esegue questa operazione, viene controllato che l'origine specificata sia registrata nel log eventi in cui viene scritto il componente e, se necessario, viene chiamata la proprietà <xref:System.Diagnostics.EventLog.CreateEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="b0ce6-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b0ce6-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b0ce6-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b0ce6-107">Rimuovere l'associazione tra l'origine e il primo log usando il metodo <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="b0ce6-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="b0ce6-108">Registrare l'origine nel nuovo log.</span><span class="sxs-lookup"><span data-stu-id="b0ce6-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ce6-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0ce6-109">See also</span></span>

- [<span data-ttu-id="b0ce6-110">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="b0ce6-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
