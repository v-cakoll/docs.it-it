---
title: Utilizzo dell'annotazione nelle query
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8713d84af96fa69df5ace33d76ec21560dab2c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="f4678-102">Utilizzo dell'annotazione nelle query</span><span class="sxs-lookup"><span data-stu-id="f4678-102">Using Annotation in Queries</span></span>
<span data-ttu-id="f4678-103">Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="f4678-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="f4678-104">Ad esempio, contrassegnare diversi record di rilevamento in più flussi di lavoro deve essere contrassegnato con "Mail Server" = = "Mail Server1".</span><span class="sxs-lookup"><span data-stu-id="f4678-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="f4678-105">Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f4678-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="f4678-106">Aggiunta di annotazioni</span><span class="sxs-lookup"><span data-stu-id="f4678-106">Adding Annotations</span></span>  
 <span data-ttu-id="f4678-107">Un'annotazione può essere aggiunta a una query di rilevamento come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f4678-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="f4678-108">Questi elementi delle query di rilevamento possono essere utilizzati per creare un profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f4678-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="f4678-109">all'interno della configurazione o mediante codice.</span><span class="sxs-lookup"><span data-stu-id="f4678-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4678-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4678-110">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="f4678-111">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="f4678-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [<span data-ttu-id="f4678-112">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4678-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f4678-113">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="f4678-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
