---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924319"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="8368e-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="8368e-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8368e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8368e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8368e-104">Id</span><span class="sxs-lookup"><span data-stu-id="8368e-104">ID</span></span>|<span data-ttu-id="8368e-105">1030</span><span class="sxs-lookup"><span data-stu-id="8368e-105">1030</span></span>|  
|<span data-ttu-id="8368e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8368e-106">Keywords</span></span>|<span data-ttu-id="8368e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8368e-107">WFRuntime</span></span>|  
|<span data-ttu-id="8368e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="8368e-108">Level</span></span>|<span data-ttu-id="8368e-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="8368e-109">Verbose</span></span>|  
|<span data-ttu-id="8368e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="8368e-110">Channel</span></span>|<span data-ttu-id="8368e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8368e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8368e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8368e-112">Description</span></span>  
 <span data-ttu-id="8368e-113">Indica che viene avviata l'esecuzione di FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="8368e-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8368e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8368e-114">Message</span></span>  
 <span data-ttu-id="8368e-115">Avvio dell'esecuzione di FaultWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8368e-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8368e-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="8368e-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8368e-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8368e-117">Details</span></span>  
  
|<span data-ttu-id="8368e-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="8368e-118">Data Item Name</span></span>|<span data-ttu-id="8368e-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="8368e-119">Data Item Type</span></span>|<span data-ttu-id="8368e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8368e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8368e-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="8368e-121">FaultActivity</span></span>|<span data-ttu-id="8368e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-122">xs:string</span></span>|<span data-ttu-id="8368e-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="8368e-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="8368e-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8368e-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="8368e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-125">xs:string</span></span>|<span data-ttu-id="8368e-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="8368e-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="8368e-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8368e-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="8368e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-128">xs:string</span></span>|<span data-ttu-id="8368e-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="8368e-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="8368e-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="8368e-130">ExceptionActivity</span></span>|<span data-ttu-id="8368e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-131">xs:string</span></span>|<span data-ttu-id="8368e-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8368e-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8368e-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8368e-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="8368e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-134">xs:string</span></span>|<span data-ttu-id="8368e-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8368e-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8368e-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8368e-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="8368e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-137">xs:string</span></span>|<span data-ttu-id="8368e-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8368e-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="8368e-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="8368e-139">Exception</span></span>|<span data-ttu-id="8368e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-140">xs:string</span></span>|<span data-ttu-id="8368e-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8368e-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="8368e-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8368e-142">AppDomain</span></span>|<span data-ttu-id="8368e-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="8368e-143">xs:string</span></span>|<span data-ttu-id="8368e-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8368e-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
