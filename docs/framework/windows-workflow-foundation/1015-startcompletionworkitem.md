---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032266"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="66d69-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="66d69-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="66d69-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="66d69-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66d69-104">Id</span><span class="sxs-lookup"><span data-stu-id="66d69-104">ID</span></span>|<span data-ttu-id="66d69-105">1015</span><span class="sxs-lookup"><span data-stu-id="66d69-105">1015</span></span>|  
|<span data-ttu-id="66d69-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="66d69-106">Keywords</span></span>|<span data-ttu-id="66d69-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="66d69-107">WFRuntime</span></span>|  
|<span data-ttu-id="66d69-108">Livello</span><span class="sxs-lookup"><span data-stu-id="66d69-108">Level</span></span>|<span data-ttu-id="66d69-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="66d69-109">Verbose</span></span>|  
|<span data-ttu-id="66d69-110">Canale</span><span class="sxs-lookup"><span data-stu-id="66d69-110">Channel</span></span>|<span data-ttu-id="66d69-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="66d69-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="66d69-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66d69-112">Description</span></span>  
 <span data-ttu-id="66d69-113">Indica che viene avviata l'esecuzione di CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="66d69-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="66d69-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="66d69-114">Message</span></span>  
 <span data-ttu-id="66d69-115">Avvio dell'esecuzione di CompletionWorkItem per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="66d69-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="66d69-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="66d69-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="66d69-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="66d69-117">Details</span></span>  
  
|<span data-ttu-id="66d69-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="66d69-118">Data Item Name</span></span>|<span data-ttu-id="66d69-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="66d69-119">Data Item Type</span></span>|<span data-ttu-id="66d69-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66d69-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="66d69-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="66d69-121">ParentActivity</span></span>|<span data-ttu-id="66d69-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-122">xs:string</span></span>|<span data-ttu-id="66d69-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="66d69-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="66d69-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="66d69-124">ParentDisplayName</span></span>|<span data-ttu-id="66d69-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-125">xs:string</span></span>|<span data-ttu-id="66d69-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="66d69-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="66d69-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="66d69-127">ParentInstanceId</span></span>|<span data-ttu-id="66d69-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-128">xs:string</span></span>|<span data-ttu-id="66d69-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="66d69-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="66d69-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="66d69-130">CompletedActivity</span></span>|<span data-ttu-id="66d69-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-131">xs:string</span></span>|<span data-ttu-id="66d69-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="66d69-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="66d69-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="66d69-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="66d69-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-134">xs:string</span></span>|<span data-ttu-id="66d69-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="66d69-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="66d69-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="66d69-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="66d69-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-137">xs:string</span></span>|<span data-ttu-id="66d69-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="66d69-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="66d69-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="66d69-139">AppDomain</span></span>|<span data-ttu-id="66d69-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="66d69-140">xs:string</span></span>|<span data-ttu-id="66d69-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="66d69-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
