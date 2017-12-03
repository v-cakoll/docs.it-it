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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c7f6324d6d563ca19b16a76cff809649ad90e3dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="114---workflowinstancerecordwithid"></a><span data-ttu-id="342ad-102">114 - WorkflowInstanceRecordWithId</span><span class="sxs-lookup"><span data-stu-id="342ad-102">114 - WorkflowInstanceRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="342ad-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="342ad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="342ad-104">ID</span><span class="sxs-lookup"><span data-stu-id="342ad-104">ID</span></span>|<span data-ttu-id="342ad-105">114</span><span class="sxs-lookup"><span data-stu-id="342ad-105">114</span></span>|  
|<span data-ttu-id="342ad-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="342ad-106">Keywords</span></span>|<span data-ttu-id="342ad-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="342ad-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="342ad-108">Livello</span><span class="sxs-lookup"><span data-stu-id="342ad-108">Level</span></span>|<span data-ttu-id="342ad-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="342ad-109">Information</span></span>|  
|<span data-ttu-id="342ad-110">Canale</span><span class="sxs-lookup"><span data-stu-id="342ad-110">Channel</span></span>|<span data-ttu-id="342ad-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="342ad-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="342ad-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342ad-112">Description</span></span>  
 <span data-ttu-id="342ad-113">Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea l'oggetto WorkflowInstanceRecord per gli stati del flusso di lavoro: Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span><span class="sxs-lookup"><span data-stu-id="342ad-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="342ad-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="342ad-114">Message</span></span>  
 <span data-ttu-id="342ad-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="342ad-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="342ad-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="342ad-116">Details</span></span>  
  
|<span data-ttu-id="342ad-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="342ad-117">Data Item Name</span></span>|<span data-ttu-id="342ad-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="342ad-118">Data Item Type</span></span>|<span data-ttu-id="342ad-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342ad-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="342ad-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="342ad-120">InstanceId</span></span>|<span data-ttu-id="342ad-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="342ad-121">xs:GUID</span></span>|<span data-ttu-id="342ad-122">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="342ad-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="342ad-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="342ad-123">RecordNumber</span></span>|<span data-ttu-id="342ad-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="342ad-124">xs:long</span></span>|<span data-ttu-id="342ad-125">Numero di sequenza del record creato.</span><span class="sxs-lookup"><span data-stu-id="342ad-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="342ad-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="342ad-126">EventTime</span></span>|<span data-ttu-id="342ad-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="342ad-127">xs:dateTime</span></span>|<span data-ttu-id="342ad-128">Ora di creazione dell'evento in UTC.</span><span class="sxs-lookup"><span data-stu-id="342ad-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="342ad-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="342ad-129">ActivityDefinitionId</span></span>|<span data-ttu-id="342ad-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="342ad-130">xs:string</span></span>|<span data-ttu-id="342ad-131">Nome dell'attività radice nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="342ad-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="342ad-132">Stato</span><span class="sxs-lookup"><span data-stu-id="342ad-132">State</span></span>|<span data-ttu-id="342ad-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="342ad-133">xs:string</span></span>|<span data-ttu-id="342ad-134">Stato corrente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="342ad-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="342ad-135">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="342ad-135">Annotations</span></span>|<span data-ttu-id="342ad-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="342ad-136">xs:string</span></span>|<span data-ttu-id="342ad-137">Annotazioni aggiunte a questo evento.</span><span class="sxs-lookup"><span data-stu-id="342ad-137">The annotations that were added to this event.</span></span> <span data-ttu-id="342ad-138">I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="342ad-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="342ad-139">Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >.</span><span class="sxs-lookup"><span data-stu-id="342ad-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="342ad-140">La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="342ad-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="342ad-141">Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="342ad-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="342ad-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="342ad-142">ProfileName</span></span>|<span data-ttu-id="342ad-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="342ad-143">xs:string</span></span>|<span data-ttu-id="342ad-144">Nome o profilo di rilevamento che ha determinato la creazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="342ad-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="342ad-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="342ad-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="342ad-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="342ad-146">xs:string</span></span>|<span data-ttu-id="342ad-147">ID della definizione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="342ad-147">The workflow definition id</span></span>|  
|<span data-ttu-id="342ad-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="342ad-148">AppDomain</span></span>|<span data-ttu-id="342ad-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="342ad-149">xs:string</span></span>|<span data-ttu-id="342ad-150">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="342ad-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
