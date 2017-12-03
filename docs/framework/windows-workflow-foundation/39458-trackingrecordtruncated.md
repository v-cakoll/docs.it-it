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
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="8c63a-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="8c63a-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="8c63a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8c63a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c63a-104">ID</span><span class="sxs-lookup"><span data-stu-id="8c63a-104">ID</span></span>|<span data-ttu-id="8c63a-105">39458</span><span class="sxs-lookup"><span data-stu-id="8c63a-105">39458</span></span>|  
|<span data-ttu-id="8c63a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8c63a-106">Keywords</span></span>|<span data-ttu-id="8c63a-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="8c63a-107">WFTracking</span></span>|  
|<span data-ttu-id="8c63a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="8c63a-108">Level</span></span>|<span data-ttu-id="8c63a-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="8c63a-109">Warning</span></span>|  
|<span data-ttu-id="8c63a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="8c63a-110">Channel</span></span>|<span data-ttu-id="8c63a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8c63a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8c63a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c63a-112">Description</span></span>  
 <span data-ttu-id="8c63a-113">Indica che un record di rilevamento è stato troncato.</span><span class="sxs-lookup"><span data-stu-id="8c63a-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="8c63a-114">Variabili/annotazioni/dati utente rimossi.</span><span class="sxs-lookup"><span data-stu-id="8c63a-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8c63a-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8c63a-115">Message</span></span>  
 <span data-ttu-id="8c63a-116">Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2.</span><span class="sxs-lookup"><span data-stu-id="8c63a-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="8c63a-117">Variabili/annotazioni/dati utente rimossi</span><span class="sxs-lookup"><span data-stu-id="8c63a-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="8c63a-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8c63a-118">Details</span></span>  
  
|<span data-ttu-id="8c63a-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="8c63a-119">Data Item Name</span></span>|<span data-ttu-id="8c63a-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="8c63a-120">Data Item Type</span></span>|<span data-ttu-id="8c63a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c63a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8c63a-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="8c63a-122">RecordNumber</span></span>|<span data-ttu-id="8c63a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c63a-123">xs:string</span></span>|<span data-ttu-id="8c63a-124">Numero del record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8c63a-124">The tracking record number.</span></span>|  
|<span data-ttu-id="8c63a-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="8c63a-125">ProviderId</span></span>|<span data-ttu-id="8c63a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c63a-126">xs:string</span></span>|<span data-ttu-id="8c63a-127">ID del provider ETW.</span><span class="sxs-lookup"><span data-stu-id="8c63a-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="8c63a-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8c63a-128">AppDomain</span></span>|<span data-ttu-id="8c63a-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c63a-129">xs:string</span></span>|<span data-ttu-id="8c63a-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8c63a-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
