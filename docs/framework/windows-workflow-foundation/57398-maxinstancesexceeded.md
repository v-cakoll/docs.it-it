---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945964"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="698a6-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="698a6-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="698a6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="698a6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="698a6-104">Id</span><span class="sxs-lookup"><span data-stu-id="698a6-104">ID</span></span>|<span data-ttu-id="698a6-105">57398</span><span class="sxs-lookup"><span data-stu-id="698a6-105">57398</span></span>|  
|<span data-ttu-id="698a6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="698a6-106">Keywords</span></span>|<span data-ttu-id="698a6-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="698a6-107">WFServices</span></span>|  
|<span data-ttu-id="698a6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="698a6-108">Level</span></span>|<span data-ttu-id="698a6-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="698a6-109">Warning</span></span>|  
|<span data-ttu-id="698a6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="698a6-110">Channel</span></span>|<span data-ttu-id="698a6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="698a6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="698a6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="698a6-112">Description</span></span>  
 <span data-ttu-id="698a6-113">Indica che il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="698a6-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="698a6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="698a6-114">Message</span></span>  
 <span data-ttu-id="698a6-115">Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="698a6-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="698a6-116">Il limite per questa velocità è stato impostato su %1.</span><span class="sxs-lookup"><span data-stu-id="698a6-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="698a6-117">Il valore della velocità può essere modificato cambiando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="698a6-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="698a6-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="698a6-118">Details</span></span>  
  
|<span data-ttu-id="698a6-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="698a6-119">Data Item Name</span></span>|<span data-ttu-id="698a6-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="698a6-120">Data Item Type</span></span>|<span data-ttu-id="698a6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="698a6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="698a6-122">Nome</span><span class="sxs-lookup"><span data-stu-id="698a6-122">Name</span></span>|<span data-ttu-id="698a6-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="698a6-123">xs:string</span></span>|<span data-ttu-id="698a6-124">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="698a6-124">The name of the item.</span></span>|  
|<span data-ttu-id="698a6-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="698a6-125">AppDomain</span></span>|<span data-ttu-id="698a6-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="698a6-126">xs:string</span></span>|<span data-ttu-id="698a6-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="698a6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
