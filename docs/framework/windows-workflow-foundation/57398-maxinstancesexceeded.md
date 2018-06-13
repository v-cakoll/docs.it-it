---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512551"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="e8f67-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="e8f67-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="e8f67-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e8f67-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8f67-104">ID</span><span class="sxs-lookup"><span data-stu-id="e8f67-104">ID</span></span>|<span data-ttu-id="e8f67-105">57398</span><span class="sxs-lookup"><span data-stu-id="e8f67-105">57398</span></span>|  
|<span data-ttu-id="e8f67-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e8f67-106">Keywords</span></span>|<span data-ttu-id="e8f67-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e8f67-107">WFServices</span></span>|  
|<span data-ttu-id="e8f67-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e8f67-108">Level</span></span>|<span data-ttu-id="e8f67-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="e8f67-109">Warning</span></span>|  
|<span data-ttu-id="e8f67-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e8f67-110">Channel</span></span>|<span data-ttu-id="e8f67-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e8f67-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e8f67-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8f67-112">Description</span></span>  
 <span data-ttu-id="e8f67-113">Indica che il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="e8f67-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e8f67-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e8f67-114">Message</span></span>  
 <span data-ttu-id="e8f67-115">Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="e8f67-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="e8f67-116">Il limite per questa velocità è stato impostato su %1.</span><span class="sxs-lookup"><span data-stu-id="e8f67-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="e8f67-117">Il valore della velocità può essere modificato cambiando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="e8f67-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e8f67-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e8f67-118">Details</span></span>  
  
|<span data-ttu-id="e8f67-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e8f67-119">Data Item Name</span></span>|<span data-ttu-id="e8f67-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e8f67-120">Data Item Type</span></span>|<span data-ttu-id="e8f67-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8f67-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e8f67-122">Nome</span><span class="sxs-lookup"><span data-stu-id="e8f67-122">Name</span></span>|<span data-ttu-id="e8f67-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8f67-123">xs:string</span></span>|<span data-ttu-id="e8f67-124">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e8f67-124">The name of the item.</span></span>|  
|<span data-ttu-id="e8f67-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e8f67-125">AppDomain</span></span>|<span data-ttu-id="e8f67-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8f67-126">xs:string</span></span>|<span data-ttu-id="e8f67-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e8f67-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
