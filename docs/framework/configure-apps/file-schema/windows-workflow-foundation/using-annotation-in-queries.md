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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a6edccba458bfd3629cab851c5d818a69d26173
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="0c66b-102">Utilizzo dell'annotazione nelle query</span><span class="sxs-lookup"><span data-stu-id="0c66b-102">Using Annotation in Queries</span></span>
<span data-ttu-id="0c66b-103">Le annotazioni consentono di contrassegnare in modo arbitrario mediante tag i record di rilevamento con un valore che può essere configurato dopo la compilazione.</span><span class="sxs-lookup"><span data-stu-id="0c66b-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="0c66b-104">Ad esempio, contrassegnare diversi record di rilevamento in più flussi di lavoro deve essere contrassegnato con "Mail Server" = = "Mail Server1".</span><span class="sxs-lookup"><span data-stu-id="0c66b-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="0c66b-105">Questo consente di individuare facilmente tutti i record con tale tag quando si esegue una query sui record di rilevamento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0c66b-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="0c66b-106">Aggiunta di annotazioni</span><span class="sxs-lookup"><span data-stu-id="0c66b-106">Adding Annotations</span></span>  
 <span data-ttu-id="0c66b-107">Un'annotazione può essere aggiunta a una query di rilevamento come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0c66b-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="0c66b-108">Questi elementi delle query di rilevamento possono essere utilizzati per creare un profilo di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0c66b-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="0c66b-109">all'interno della configurazione o mediante codice.</span><span class="sxs-lookup"><span data-stu-id="0c66b-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c66b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c66b-110">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="0c66b-111">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="0c66b-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [<span data-ttu-id="0c66b-112">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0c66b-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0c66b-113">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0c66b-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
