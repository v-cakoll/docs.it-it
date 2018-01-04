---
title: Runnable Instances Detection Period
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 561ef96b6f043956822a1290d4a03a2e7411f6f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="runnable-instances-detection-period"></a><span data-ttu-id="0b561-102">Runnable Instances Detection Period</span><span class="sxs-lookup"><span data-stu-id="0b561-102">Runnable Instances Detection Period</span></span>
<span data-ttu-id="0b561-103">L'archivio di istanze del flusso di lavoro SQL esegue un'attività interna che attiva e rileva periodicamente istanze eseguibili o attivabili nel database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="0b561-103">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects runnable or activatable instances in the persistence database.</span></span> <span data-ttu-id="0b561-104">Il **Runnable Instances Detection Period** proprietà dell'archivio di istanze del flusso di lavoro SQL specifica il periodo di tempo trascorso il quale l'archivio di istanze del flusso di lavoro SQL esegue un'attività di rilevamento per rilevare qualsiasi flusso di lavoro eseguibile o attivabili istanze nel database di persistenza dopo il ciclo di rilevamento precedente.</span><span class="sxs-lookup"><span data-stu-id="0b561-104">The **Runnable Instances Detection Period** property of the SQL Workflow Instance Store specifies the time period after which the SQL Workflow Instance Store runs a detection task to detect any runnable or activatable workflow instances in the persistence database after the previous detection cycle.</span></span>  
  
 <span data-ttu-id="0b561-105">L'impostazione di un intervallo più breve per questa proprietà riduce il tempo tra la scadenza di un timer associato a un'istanza del flusso di lavoro e la segnalazione dell'evento e il successivo caricamento dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="0b561-105">Setting a shorter interval for this property reduces the time between the expiration of a timer associated with a workflow instance and the signaling of the event and subsequent loading of the instance.</span></span> <span data-ttu-id="0b561-106">Tuttavia, aumenta anche il carico di elaborazione su un host e ciò può risultare non appropriato in scenari con timer durevoli e/o errori host.</span><span class="sxs-lookup"><span data-stu-id="0b561-106">However, it also increases the processing load on a host and may not be desirable in scenarios where durable timers and/or host failures are rare.</span></span> <span data-ttu-id="0b561-107">Il tipo della proprietà è TimeSpan e il valore della proprietà segue il formato: hh:mm:ss.</span><span class="sxs-lookup"><span data-stu-id="0b561-107">The type of the property is TimeSpan and the value of the property follows the format: hh:mm:ss.</span></span> <span data-ttu-id="0b561-108">Il valore minimo per questa proprietà è 00:00:01.</span><span class="sxs-lookup"><span data-stu-id="0b561-108">The minimum value for this property is 00:00:01.</span></span> <span data-ttu-id="0b561-109">Il valore predefinito della proprietà è 00:00:05.</span><span class="sxs-lookup"><span data-stu-id="0b561-109">The default value for the property is 00:00:05.</span></span>  
  
 <span data-ttu-id="0b561-110">Per ulteriori informazioni vedere rilevamento e attivazione di istanze del flusso di lavoro eseguibili e attivabile, [attivazione di istanze](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span><span class="sxs-lookup"><span data-stu-id="0b561-110">For more information detecting and activating runnable and activatable workflow instances, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span>
