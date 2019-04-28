---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924852"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="bf051-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="bf051-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="bf051-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bf051-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf051-104">Id</span><span class="sxs-lookup"><span data-stu-id="bf051-104">ID</span></span>|<span data-ttu-id="bf051-105">1035</span><span class="sxs-lookup"><span data-stu-id="bf051-105">1035</span></span>|  
|<span data-ttu-id="bf051-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="bf051-106">Keywords</span></span>|<span data-ttu-id="bf051-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bf051-107">WFRuntime</span></span>|  
|<span data-ttu-id="bf051-108">Livello</span><span class="sxs-lookup"><span data-stu-id="bf051-108">Level</span></span>|<span data-ttu-id="bf051-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="bf051-109">Verbose</span></span>|  
|<span data-ttu-id="bf051-110">Canale</span><span class="sxs-lookup"><span data-stu-id="bf051-110">Channel</span></span>|<span data-ttu-id="bf051-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bf051-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bf051-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf051-112">Description</span></span>  
 <span data-ttu-id="bf051-113">Indica che un'attività ha impostato la transazione runtime.</span><span class="sxs-lookup"><span data-stu-id="bf051-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bf051-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="bf051-114">Message</span></span>  
 <span data-ttu-id="bf051-115">La transazione di runtime è stata impostata dall'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="bf051-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="bf051-116">Esecuzione isolata all'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="bf051-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bf051-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bf051-117">Details</span></span>  
  
|<span data-ttu-id="bf051-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="bf051-118">Data Item Name</span></span>|<span data-ttu-id="bf051-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="bf051-119">Data Item Type</span></span>|<span data-ttu-id="bf051-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf051-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bf051-121">Attività</span><span class="sxs-lookup"><span data-stu-id="bf051-121">Activity</span></span>|<span data-ttu-id="bf051-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-122">xs:string</span></span>|<span data-ttu-id="bf051-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="bf051-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="bf051-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bf051-124">DisplayName</span></span>|<span data-ttu-id="bf051-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-125">xs:string</span></span>|<span data-ttu-id="bf051-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="bf051-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="bf051-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bf051-127">InstanceId</span></span>|<span data-ttu-id="bf051-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-128">xs:string</span></span>|<span data-ttu-id="bf051-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="bf051-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bf051-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="bf051-130">IsolatedActivity</span></span>|<span data-ttu-id="bf051-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-131">xs:string</span></span>|<span data-ttu-id="bf051-132">Il nome del tipo di attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="bf051-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="bf051-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="bf051-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="bf051-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-134">xs:string</span></span>|<span data-ttu-id="bf051-135">Il nome visualizzato dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="bf051-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="bf051-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="bf051-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="bf051-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-137">xs:string</span></span>|<span data-ttu-id="bf051-138">L'ID istanza dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="bf051-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="bf051-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bf051-139">AppDomain</span></span>|<span data-ttu-id="bf051-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="bf051-140">xs:string</span></span>|<span data-ttu-id="bf051-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bf051-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
