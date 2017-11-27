---
title: 115 - WorkflowInstanceAbortedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0293dd4e-e6ae-473a-b3d6-c2d38f9bd875
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e50ba59a52a899a06b334ef2906126f5a215ad6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="115---workflowinstanceabortedrecordwithid"></a><span data-ttu-id="52929-102">115 - WorkflowInstanceAbortedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="52929-102">115 - WorkflowInstanceAbortedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="52929-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="52929-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52929-104">ID</span><span class="sxs-lookup"><span data-stu-id="52929-104">ID</span></span>|<span data-ttu-id="52929-105">115</span><span class="sxs-lookup"><span data-stu-id="52929-105">115</span></span>|  
|<span data-ttu-id="52929-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="52929-106">Keywords</span></span>|<span data-ttu-id="52929-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="52929-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="52929-108">Livello</span><span class="sxs-lookup"><span data-stu-id="52929-108">Level</span></span>|<span data-ttu-id="52929-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="52929-109">Warning</span></span>|  
|<span data-ttu-id="52929-110">Canale</span><span class="sxs-lookup"><span data-stu-id="52929-110">Channel</span></span>|<span data-ttu-id="52929-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="52929-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="52929-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52929-112">Description</span></span>  
 <span data-ttu-id="52929-113">Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea WorkflowInstanceAbortedRecord.</span><span class="sxs-lookup"><span data-stu-id="52929-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceAbortedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="52929-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="52929-114">Message</span></span>  
 <span data-ttu-id="52929-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="52929-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="52929-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="52929-116">Details</span></span>  
  
|<span data-ttu-id="52929-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="52929-117">Data Item Name</span></span>|<span data-ttu-id="52929-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="52929-118">Data Item Type</span></span>|<span data-ttu-id="52929-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52929-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="52929-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="52929-120">InstanceId</span></span>|<span data-ttu-id="52929-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="52929-121">xs:GUID</span></span>|<span data-ttu-id="52929-122">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="52929-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="52929-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="52929-123">RecordNumber</span></span>|<span data-ttu-id="52929-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="52929-124">xs:long</span></span>|<span data-ttu-id="52929-125">Numero di sequenza del record creato.</span><span class="sxs-lookup"><span data-stu-id="52929-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="52929-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="52929-126">EventTime</span></span>|<span data-ttu-id="52929-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="52929-127">xs:dateTime</span></span>|<span data-ttu-id="52929-128">Ora di creazione dell'evento in UTC.</span><span class="sxs-lookup"><span data-stu-id="52929-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="52929-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="52929-129">ActivityDefinitionId</span></span>|<span data-ttu-id="52929-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="52929-130">xs:string</span></span>|<span data-ttu-id="52929-131">Nome dell'attività radice nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="52929-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="52929-132">Stato</span><span class="sxs-lookup"><span data-stu-id="52929-132">State</span></span>|<span data-ttu-id="52929-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="52929-133">xs:string</span></span>|<span data-ttu-id="52929-134">Stato corrente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="52929-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="52929-135">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="52929-135">Annotations</span></span>|<span data-ttu-id="52929-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="52929-136">xs:string</span></span>|<span data-ttu-id="52929-137">Annotazioni aggiunte a questo evento.</span><span class="sxs-lookup"><span data-stu-id="52929-137">The annotations that were added to this event.</span></span> <span data-ttu-id="52929-138">I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="52929-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="52929-139">Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >.</span><span class="sxs-lookup"><span data-stu-id="52929-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="52929-140">La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="52929-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="52929-141">Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="52929-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="52929-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="52929-142">ProfileName</span></span>|<span data-ttu-id="52929-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="52929-143">xs:string</span></span>|<span data-ttu-id="52929-144">Nome o profilo di rilevamento che ha determinato la creazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="52929-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="52929-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="52929-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="52929-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="52929-146">xs:string</span></span>|<span data-ttu-id="52929-147">ID della definizione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="52929-147">The workflow definition id</span></span>|  
|<span data-ttu-id="52929-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="52929-148">AppDomain</span></span>|<span data-ttu-id="52929-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="52929-149">xs:string</span></span>|<span data-ttu-id="52929-150">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="52929-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
