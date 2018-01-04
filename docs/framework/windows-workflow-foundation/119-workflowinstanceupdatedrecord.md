---
title: 119 - WorkflowInstanceUpdatedRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2cb60a0f7905f49e4bfa4c1c50de686dd74ff114
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="119---workflowinstanceupdatedrecord"></a><span data-ttu-id="a36c6-102">119 - WorkflowInstanceUpdatedRecord</span><span class="sxs-lookup"><span data-stu-id="a36c6-102">119 - WorkflowInstanceUpdatedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="a36c6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a36c6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a36c6-104">ID</span><span class="sxs-lookup"><span data-stu-id="a36c6-104">ID</span></span>|<span data-ttu-id="a36c6-105">119</span><span class="sxs-lookup"><span data-stu-id="a36c6-105">119</span></span>|  
|<span data-ttu-id="a36c6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a36c6-106">Keywords</span></span>|<span data-ttu-id="a36c6-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="a36c6-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="a36c6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a36c6-108">Level</span></span>|<span data-ttu-id="a36c6-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="a36c6-109">Information</span></span>|  
|<span data-ttu-id="a36c6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a36c6-110">Channel</span></span>|<span data-ttu-id="a36c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a36c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a36c6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a36c6-112">Description</span></span>  
 <span data-ttu-id="a36c6-113">Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="a36c6-113">This event is emitted by the ETW tracking participant when a workflow instance is updated.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a36c6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a36c6-114">Message</span></span>  
 <span data-ttu-id="a36c6-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span><span class="sxs-lookup"><span data-stu-id="a36c6-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span></span>  
  
## <a name="details"></a><span data-ttu-id="a36c6-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a36c6-116">Details</span></span>  
  
|<span data-ttu-id="a36c6-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a36c6-117">Data Item Name</span></span>|<span data-ttu-id="a36c6-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a36c6-118">Data Item Type</span></span>|<span data-ttu-id="a36c6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a36c6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a36c6-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a36c6-120">InstanceId</span></span>|<span data-ttu-id="a36c6-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="a36c6-121">xs:GUID</span></span>|<span data-ttu-id="a36c6-122">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a36c6-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a36c6-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="a36c6-123">RecordNumber</span></span>|<span data-ttu-id="a36c6-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="a36c6-124">xs:long</span></span>|<span data-ttu-id="a36c6-125">Numero di sequenza del record creato.</span><span class="sxs-lookup"><span data-stu-id="a36c6-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="a36c6-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="a36c6-126">EventTime</span></span>|<span data-ttu-id="a36c6-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="a36c6-127">xs:dateTime</span></span>|<span data-ttu-id="a36c6-128">Ora di creazione dell'evento in UTC.</span><span class="sxs-lookup"><span data-stu-id="a36c6-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="a36c6-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="a36c6-129">ActivityDefinitionId</span></span>|<span data-ttu-id="a36c6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-130">xs:string</span></span>|<span data-ttu-id="a36c6-131">Nome dell'attività radice nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a36c6-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="a36c6-132">Stato</span><span class="sxs-lookup"><span data-stu-id="a36c6-132">State</span></span>|<span data-ttu-id="a36c6-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-133">xs:string</span></span>|<span data-ttu-id="a36c6-134">Stato corrente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a36c6-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="a36c6-135">OriginalDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a36c6-135">OriginalDefinitionIdentity</span></span>|<span data-ttu-id="a36c6-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-136">xs:string</span></span>|<span data-ttu-id="a36c6-137">ID definizione originale del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a36c6-137">The original workflow definition id</span></span>|  
|<span data-ttu-id="a36c6-138">UpdatedDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a36c6-138">UpdatedDefinitionIdentity</span></span>|<span data-ttu-id="a36c6-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-139">xs:string</span></span>|<span data-ttu-id="a36c6-140">ID definizione aggiornata del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a36c6-140">The updated workflow definition id</span></span>|  
|<span data-ttu-id="a36c6-141">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="a36c6-141">Annotations</span></span>|<span data-ttu-id="a36c6-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-142">xs:string</span></span>|<span data-ttu-id="a36c6-143">Annotazioni aggiunte a questo evento.</span><span class="sxs-lookup"><span data-stu-id="a36c6-143">The annotations that were added to this event.</span></span> <span data-ttu-id="a36c6-144">I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="a36c6-144">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="a36c6-145">Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >.</span><span class="sxs-lookup"><span data-stu-id="a36c6-145">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="a36c6-146">La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="a36c6-146">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="a36c6-147">Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="a36c6-147">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="a36c6-148">ProfileName</span><span class="sxs-lookup"><span data-stu-id="a36c6-148">ProfileName</span></span>|<span data-ttu-id="a36c6-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-149">xs:string</span></span>|<span data-ttu-id="a36c6-150">Nome o profilo di rilevamento che ha determinato la creazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="a36c6-150">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="a36c6-151">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a36c6-151">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="a36c6-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-152">xs:string</span></span>|<span data-ttu-id="a36c6-153">ID della definizione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a36c6-153">The workflow definition id</span></span>|  
|<span data-ttu-id="a36c6-154">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a36c6-154">AppDomain</span></span>|<span data-ttu-id="a36c6-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="a36c6-155">xs:string</span></span>|<span data-ttu-id="a36c6-156">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a36c6-156">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
