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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 314f880f1fc2d78efc59f73f37122d03ae30cf72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="115---workflowinstanceabortedrecordwithid"></a><span data-ttu-id="d3ed7-102">115 - WorkflowInstanceAbortedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="d3ed7-102">115 - WorkflowInstanceAbortedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="d3ed7-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d3ed7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3ed7-104">ID</span><span class="sxs-lookup"><span data-stu-id="d3ed7-104">ID</span></span>|<span data-ttu-id="d3ed7-105">115</span><span class="sxs-lookup"><span data-stu-id="d3ed7-105">115</span></span>|  
|<span data-ttu-id="d3ed7-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d3ed7-106">Keywords</span></span>|<span data-ttu-id="d3ed7-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="d3ed7-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="d3ed7-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d3ed7-108">Level</span></span>|<span data-ttu-id="d3ed7-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="d3ed7-109">Warning</span></span>|  
|<span data-ttu-id="d3ed7-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d3ed7-110">Channel</span></span>|<span data-ttu-id="d3ed7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d3ed7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d3ed7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3ed7-112">Description</span></span>  
 <span data-ttu-id="d3ed7-113">Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea WorkflowInstanceAbortedRecord.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceAbortedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d3ed7-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d3ed7-114">Message</span></span>  
 <span data-ttu-id="d3ed7-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="d3ed7-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="d3ed7-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d3ed7-116">Details</span></span>  
  
|<span data-ttu-id="d3ed7-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d3ed7-117">Data Item Name</span></span>|<span data-ttu-id="d3ed7-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d3ed7-118">Data Item Type</span></span>|<span data-ttu-id="d3ed7-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3ed7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d3ed7-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d3ed7-120">InstanceId</span></span>|<span data-ttu-id="d3ed7-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="d3ed7-121">xs:GUID</span></span>|<span data-ttu-id="d3ed7-122">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="d3ed7-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="d3ed7-123">RecordNumber</span></span>|<span data-ttu-id="d3ed7-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="d3ed7-124">xs:long</span></span>|<span data-ttu-id="d3ed7-125">Numero di sequenza del record creato.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="d3ed7-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="d3ed7-126">EventTime</span></span>|<span data-ttu-id="d3ed7-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="d3ed7-127">xs:dateTime</span></span>|<span data-ttu-id="d3ed7-128">Ora di creazione dell'evento in UTC.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="d3ed7-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="d3ed7-129">ActivityDefinitionId</span></span>|<span data-ttu-id="d3ed7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3ed7-130">xs:string</span></span>|<span data-ttu-id="d3ed7-131">Nome dell'attività radice nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="d3ed7-132">Stato</span><span class="sxs-lookup"><span data-stu-id="d3ed7-132">State</span></span>|<span data-ttu-id="d3ed7-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3ed7-133">xs:string</span></span>|<span data-ttu-id="d3ed7-134">Stato corrente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="d3ed7-135">Annotazioni</span><span class="sxs-lookup"><span data-stu-id="d3ed7-135">Annotations</span></span>|<span data-ttu-id="d3ed7-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3ed7-136">xs:string</span></span>|<span data-ttu-id="d3ed7-137">Annotazioni aggiunte a questo evento.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-137">The annotations that were added to this event.</span></span> <span data-ttu-id="d3ed7-138">I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="d3ed7-139">Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="d3ed7-140">La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="d3ed7-141">Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="d3ed7-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="d3ed7-142">ProfileName</span></span>|<span data-ttu-id="d3ed7-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3ed7-143">xs:string</span></span>|<span data-ttu-id="d3ed7-144">Nome o profilo di rilevamento che ha determinato la creazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="d3ed7-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="d3ed7-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="d3ed7-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3ed7-146">xs:string</span></span>|<span data-ttu-id="d3ed7-147">ID della definizione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d3ed7-147">The workflow definition id</span></span>|  
|<span data-ttu-id="d3ed7-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d3ed7-148">AppDomain</span></span>|<span data-ttu-id="d3ed7-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="d3ed7-149">xs:string</span></span>|<span data-ttu-id="d3ed7-150">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d3ed7-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
