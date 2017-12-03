---
title: 116 - WorkflowInstanceSuspendedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38232c03-6139-4494-a020-79bc83eb9dce
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59b77e2fac36dea3afce77a74e0ccacb432a2ada
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="116---workflowinstancesuspendedrecordwithid"></a><span data-ttu-id="d8d42-102">116 - WorkflowInstanceSuspendedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="d8d42-102">116 - WorkflowInstanceSuspendedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="d8d42-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d8d42-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8d42-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8d42-104">ID</span></span>|<span data-ttu-id="d8d42-105">116</span><span class="sxs-lookup"><span data-stu-id="d8d42-105">116</span></span>|  
|<span data-ttu-id="d8d42-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d8d42-106">Keywords</span></span>|<span data-ttu-id="d8d42-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="d8d42-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="d8d42-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d8d42-108">Level</span></span>|<span data-ttu-id="d8d42-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="d8d42-109">Information</span></span>|  
|<span data-ttu-id="d8d42-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d8d42-110">Channel</span></span>|<span data-ttu-id="d8d42-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d8d42-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8d42-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8d42-112">Description</span></span>  
 <span data-ttu-id="d8d42-113">Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea l'oggetto WorkflowInstanceSuspendedRecord.</span><span class="sxs-lookup"><span data-stu-id="d8d42-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8d42-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8d42-114">Message</span></span>  
 <span data-ttu-id="d8d42-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="d8d42-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8d42-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d8d42-116">Details</span></span>  
  
|<span data-ttu-id="d8d42-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d8d42-117">Data Item Name</span></span>|<span data-ttu-id="d8d42-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d8d42-118">Data Item Type</span></span>|<span data-ttu-id="d8d42-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8d42-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8d42-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d8d42-120">InstanceId</span></span>|<span data-ttu-id="d8d42-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="d8d42-121">xs:GUID</span></span>|<span data-ttu-id="d8d42-122">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8d42-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="d8d42-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="d8d42-123">RecordNumber</span></span>|<span data-ttu-id="d8d42-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="d8d42-124">xs:long</span></span>|<span data-ttu-id="d8d42-125">Numero di sequenza del record creato.</span><span class="sxs-lookup"><span data-stu-id="d8d42-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="d8d42-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="d8d42-126">EventTime</span></span>|<span data-ttu-id="d8d42-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="d8d42-127">xs:dateTime</span></span>|<span data-ttu-id="d8d42-128">Ora di creazione dell'evento in UTC.</span><span class="sxs-lookup"><span data-stu-id="d8d42-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="d8d42-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="d8d42-129">ActivityDefinitionId</span></span>|<span data-ttu-id="d8d42-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d42-130">xs:string</span></span>|<span data-ttu-id="d8d42-131">Nome dell'attività radice nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8d42-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="d8d42-132">Stato</span><span class="sxs-lookup"><span data-stu-id="d8d42-132">State</span></span>|<span data-ttu-id="d8d42-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d42-133">xs:string</span></span>|<span data-ttu-id="d8d42-134">Stato corrente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8d42-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="d8d42-135">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="d8d42-135">Annotations</span></span>|<span data-ttu-id="d8d42-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d42-136">xs:string</span></span>|<span data-ttu-id="d8d42-137">Annotazioni aggiunte a questo evento.</span><span class="sxs-lookup"><span data-stu-id="d8d42-137">The annotations that were added to this event.</span></span> <span data-ttu-id="d8d42-138">I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="d8d42-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="d8d42-139">Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >.</span><span class="sxs-lookup"><span data-stu-id="d8d42-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="d8d42-140">La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="d8d42-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="d8d42-141">Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="d8d42-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="d8d42-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="d8d42-142">ProfileName</span></span>|<span data-ttu-id="d8d42-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d42-143">xs:string</span></span>|<span data-ttu-id="d8d42-144">Nome o profilo di rilevamento che ha determinato la creazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="d8d42-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="d8d42-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="d8d42-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="d8d42-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d42-146">xs:string</span></span>|<span data-ttu-id="d8d42-147">ID della definizione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8d42-147">The workflow definition id</span></span>|  
|<span data-ttu-id="d8d42-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8d42-148">AppDomain</span></span>|<span data-ttu-id="d8d42-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8d42-149">xs:string</span></span>|<span data-ttu-id="d8d42-150">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d8d42-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
