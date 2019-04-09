---
title: Utilizzo dell'annotazione nelle query
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: fd2d98852ca44e3485ddcf4be29d505b39011698
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208644"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="dad30-102">Utilizzo dell'annotazione nelle query</span><span class="sxs-lookup"><span data-stu-id="dad30-102">Using Annotation in Queries</span></span>
<span data-ttu-id="dad30-103">Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="dad30-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="dad30-104">Ad esempio, è possibile diversi record di rilevamento in diversi flussi di lavoro deve essere contrassegnato con "Mail Server" = = "Mail Server1".</span><span class="sxs-lookup"><span data-stu-id="dad30-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="dad30-105">Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="dad30-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="dad30-106">Aggiunta di annotazioni</span><span class="sxs-lookup"><span data-stu-id="dad30-106">Adding Annotations</span></span>  
 <span data-ttu-id="dad30-107">Un'annotazione può essere aggiunta a una query di rilevamento come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="dad30-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="dad30-108">Questi elementi delle query di rilevamento possono essere utilizzati per creare un profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dad30-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="dad30-109">all'interno della configurazione o mediante codice.</span><span class="sxs-lookup"><span data-stu-id="dad30-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad30-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dad30-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="dad30-111">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="dad30-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)
- [<span data-ttu-id="dad30-112">Rilevamento e traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="dad30-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dad30-113">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="dad30-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
