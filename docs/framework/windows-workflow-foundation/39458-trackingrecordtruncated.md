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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecf18d6d751edd47dbeca7d2e5f4491892e41e6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="7c535-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="7c535-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="7c535-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7c535-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c535-104">ID</span><span class="sxs-lookup"><span data-stu-id="7c535-104">ID</span></span>|<span data-ttu-id="7c535-105">39458</span><span class="sxs-lookup"><span data-stu-id="7c535-105">39458</span></span>|  
|<span data-ttu-id="7c535-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7c535-106">Keywords</span></span>|<span data-ttu-id="7c535-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="7c535-107">WFTracking</span></span>|  
|<span data-ttu-id="7c535-108">Livello</span><span class="sxs-lookup"><span data-stu-id="7c535-108">Level</span></span>|<span data-ttu-id="7c535-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="7c535-109">Warning</span></span>|  
|<span data-ttu-id="7c535-110">Canale</span><span class="sxs-lookup"><span data-stu-id="7c535-110">Channel</span></span>|<span data-ttu-id="7c535-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7c535-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7c535-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c535-112">Description</span></span>  
 <span data-ttu-id="7c535-113">Indica che un record di rilevamento è stato troncato.</span><span class="sxs-lookup"><span data-stu-id="7c535-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="7c535-114">Variabili/annotazioni/dati utente rimossi.</span><span class="sxs-lookup"><span data-stu-id="7c535-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7c535-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="7c535-115">Message</span></span>  
 <span data-ttu-id="7c535-116">Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2.</span><span class="sxs-lookup"><span data-stu-id="7c535-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="7c535-117">Variabili/annotazioni/dati utente rimossi</span><span class="sxs-lookup"><span data-stu-id="7c535-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="7c535-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7c535-118">Details</span></span>  
  
|<span data-ttu-id="7c535-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="7c535-119">Data Item Name</span></span>|<span data-ttu-id="7c535-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="7c535-120">Data Item Type</span></span>|<span data-ttu-id="7c535-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c535-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7c535-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="7c535-122">RecordNumber</span></span>|<span data-ttu-id="7c535-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c535-123">xs:string</span></span>|<span data-ttu-id="7c535-124">Numero del record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="7c535-124">The tracking record number.</span></span>|  
|<span data-ttu-id="7c535-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="7c535-125">ProviderId</span></span>|<span data-ttu-id="7c535-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c535-126">xs:string</span></span>|<span data-ttu-id="7c535-127">ID del provider ETW.</span><span class="sxs-lookup"><span data-stu-id="7c535-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="7c535-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7c535-128">AppDomain</span></span>|<span data-ttu-id="7c535-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7c535-129">xs:string</span></span>|<span data-ttu-id="7c535-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7c535-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
