---
title: 114 - WorkflowInstanceRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 57eab386e8d0486caa98a6e2f3d2f72e9e89fab7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="114---workflowinstancerecordwithid"></a><span data-ttu-id="5e8e9-102">114 - WorkflowInstanceRecordWithId</span><span class="sxs-lookup"><span data-stu-id="5e8e9-102">114 - WorkflowInstanceRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="5e8e9-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5e8e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e8e9-104">ID</span><span class="sxs-lookup"><span data-stu-id="5e8e9-104">ID</span></span>|<span data-ttu-id="5e8e9-105">114</span><span class="sxs-lookup"><span data-stu-id="5e8e9-105">114</span></span>|  
|<span data-ttu-id="5e8e9-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5e8e9-106">Keywords</span></span>|<span data-ttu-id="5e8e9-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="5e8e9-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="5e8e9-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5e8e9-108">Level</span></span>|<span data-ttu-id="5e8e9-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="5e8e9-109">Information</span></span>|  
|<span data-ttu-id="5e8e9-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5e8e9-110">Channel</span></span>|<span data-ttu-id="5e8e9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5e8e9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5e8e9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e8e9-112">Description</span></span>  
 <span data-ttu-id="5e8e9-113">Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea l'oggetto WorkflowInstanceRecord per gli stati del flusso di lavoro: Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5e8e9-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5e8e9-114">Message</span></span>  
 <span data-ttu-id="5e8e9-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="5e8e9-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="5e8e9-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5e8e9-116">Details</span></span>  
  
|<span data-ttu-id="5e8e9-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5e8e9-117">Data Item Name</span></span>|<span data-ttu-id="5e8e9-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5e8e9-118">Data Item Type</span></span>|<span data-ttu-id="5e8e9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e8e9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5e8e9-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5e8e9-120">InstanceId</span></span>|<span data-ttu-id="5e8e9-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="5e8e9-121">xs:GUID</span></span>|<span data-ttu-id="5e8e9-122">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="5e8e9-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="5e8e9-123">RecordNumber</span></span>|<span data-ttu-id="5e8e9-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="5e8e9-124">xs:long</span></span>|<span data-ttu-id="5e8e9-125">Numero di sequenza del record creato.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="5e8e9-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="5e8e9-126">EventTime</span></span>|<span data-ttu-id="5e8e9-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="5e8e9-127">xs:dateTime</span></span>|<span data-ttu-id="5e8e9-128">Ora di creazione dell'evento in UTC.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="5e8e9-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="5e8e9-129">ActivityDefinitionId</span></span>|<span data-ttu-id="5e8e9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e8e9-130">xs:string</span></span>|<span data-ttu-id="5e8e9-131">Nome dell'attività radice nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="5e8e9-132">Stato</span><span class="sxs-lookup"><span data-stu-id="5e8e9-132">State</span></span>|<span data-ttu-id="5e8e9-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e8e9-133">xs:string</span></span>|<span data-ttu-id="5e8e9-134">Stato corrente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="5e8e9-135">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="5e8e9-135">Annotations</span></span>|<span data-ttu-id="5e8e9-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e8e9-136">xs:string</span></span>|<span data-ttu-id="5e8e9-137">Annotazioni aggiunte a questo evento.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-137">The annotations that were added to this event.</span></span> <span data-ttu-id="5e8e9-138">I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="5e8e9-139">Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="5e8e9-140">La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="5e8e9-141">Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="5e8e9-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="5e8e9-142">ProfileName</span></span>|<span data-ttu-id="5e8e9-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e8e9-143">xs:string</span></span>|<span data-ttu-id="5e8e9-144">Nome o profilo di rilevamento che ha determinato la creazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="5e8e9-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="5e8e9-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="5e8e9-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e8e9-146">xs:string</span></span>|<span data-ttu-id="5e8e9-147">ID della definizione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5e8e9-147">The workflow definition id</span></span>|  
|<span data-ttu-id="5e8e9-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5e8e9-148">AppDomain</span></span>|<span data-ttu-id="5e8e9-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e8e9-149">xs:string</span></span>|<span data-ttu-id="5e8e9-150">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5e8e9-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
