---
title: Utilizzo dell'annotazione nelle query
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 728408e744bc1eca62158fab1a7a17e985fe3b6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947291"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="209c1-102">Utilizzo dell'annotazione nelle query</span><span class="sxs-lookup"><span data-stu-id="209c1-102">Using Annotation in Queries</span></span>
<span data-ttu-id="209c1-103">Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="209c1-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="209c1-104">È possibile, ad esempio, che si desideri contrassegnare più record di rilevamento in diversi flussi di lavoro con "mail server" = = "mail Server1".</span><span class="sxs-lookup"><span data-stu-id="209c1-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="209c1-105">Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="209c1-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="209c1-106">Aggiunta di annotazioni</span><span class="sxs-lookup"><span data-stu-id="209c1-106">Adding Annotations</span></span>  
 <span data-ttu-id="209c1-107">Un'annotazione può essere aggiunta a una query di rilevamento come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="209c1-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> <span data-ttu-id="209c1-108">Questi elementi delle query di rilevamento possono essere utilizzati per creare un profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="209c1-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="209c1-109">all'interno della configurazione o mediante codice.</span><span class="sxs-lookup"><span data-stu-id="209c1-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="209c1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="209c1-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="209c1-111">\<participants></span><span class="sxs-lookup"><span data-stu-id="209c1-111">\<participants></span></span>](participants.md)
- [<span data-ttu-id="209c1-112">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="209c1-112">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="209c1-113">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="209c1-113">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
