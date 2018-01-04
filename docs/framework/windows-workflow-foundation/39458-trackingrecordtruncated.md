---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d12549d201ac621361bd6a517df6c6b53ab7aec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="f63ee-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="f63ee-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="f63ee-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f63ee-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f63ee-104">ID</span><span class="sxs-lookup"><span data-stu-id="f63ee-104">ID</span></span>|<span data-ttu-id="f63ee-105">39458</span><span class="sxs-lookup"><span data-stu-id="f63ee-105">39458</span></span>|  
|<span data-ttu-id="f63ee-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f63ee-106">Keywords</span></span>|<span data-ttu-id="f63ee-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="f63ee-107">WFTracking</span></span>|  
|<span data-ttu-id="f63ee-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f63ee-108">Level</span></span>|<span data-ttu-id="f63ee-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="f63ee-109">Warning</span></span>|  
|<span data-ttu-id="f63ee-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f63ee-110">Channel</span></span>|<span data-ttu-id="f63ee-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f63ee-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f63ee-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f63ee-112">Description</span></span>  
 <span data-ttu-id="f63ee-113">Indica che un record di rilevamento è stato troncato.</span><span class="sxs-lookup"><span data-stu-id="f63ee-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="f63ee-114">Variabili/annotazioni/dati utente rimossi.</span><span class="sxs-lookup"><span data-stu-id="f63ee-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f63ee-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f63ee-115">Message</span></span>  
 <span data-ttu-id="f63ee-116">Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2.</span><span class="sxs-lookup"><span data-stu-id="f63ee-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="f63ee-117">Variabili/annotazioni/dati utente rimossi</span><span class="sxs-lookup"><span data-stu-id="f63ee-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="f63ee-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f63ee-118">Details</span></span>  
  
|<span data-ttu-id="f63ee-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f63ee-119">Data Item Name</span></span>|<span data-ttu-id="f63ee-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f63ee-120">Data Item Type</span></span>|<span data-ttu-id="f63ee-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f63ee-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f63ee-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="f63ee-122">RecordNumber</span></span>|<span data-ttu-id="f63ee-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f63ee-123">xs:string</span></span>|<span data-ttu-id="f63ee-124">Numero del record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f63ee-124">The tracking record number.</span></span>|  
|<span data-ttu-id="f63ee-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="f63ee-125">ProviderId</span></span>|<span data-ttu-id="f63ee-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f63ee-126">xs:string</span></span>|<span data-ttu-id="f63ee-127">ID del provider ETW.</span><span class="sxs-lookup"><span data-stu-id="f63ee-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="f63ee-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f63ee-128">AppDomain</span></span>|<span data-ttu-id="f63ee-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f63ee-129">xs:string</span></span>|<span data-ttu-id="f63ee-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f63ee-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
