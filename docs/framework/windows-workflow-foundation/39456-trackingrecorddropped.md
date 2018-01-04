---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 592d7c0a3725dcb50f7911a198c9dc9b7199a0a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="e2d90-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="e2d90-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="e2d90-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e2d90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2d90-104">ID</span><span class="sxs-lookup"><span data-stu-id="e2d90-104">ID</span></span>|<span data-ttu-id="e2d90-105">39456</span><span class="sxs-lookup"><span data-stu-id="e2d90-105">39456</span></span>|  
|<span data-ttu-id="e2d90-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e2d90-106">Keywords</span></span>|<span data-ttu-id="e2d90-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="e2d90-107">WFTracking</span></span>|  
|<span data-ttu-id="e2d90-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e2d90-108">Level</span></span>|<span data-ttu-id="e2d90-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="e2d90-109">Warning</span></span>|  
|<span data-ttu-id="e2d90-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e2d90-110">Channel</span></span>|<span data-ttu-id="e2d90-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e2d90-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e2d90-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2d90-112">Description</span></span>  
 <span data-ttu-id="e2d90-113">Indica che un record di rilevamento è stato eliminato perché le dimensioni superano il massimo consentito dal provider della sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="e2d90-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e2d90-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e2d90-114">Message</span></span>  
 <span data-ttu-id="e2d90-115">La dimensione del record di rilevamento %1 supera il valore massimo consentito dalla sessione ETW per il provider %2</span><span class="sxs-lookup"><span data-stu-id="e2d90-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="e2d90-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e2d90-116">Details</span></span>  
  
|<span data-ttu-id="e2d90-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e2d90-117">Data Item Name</span></span>|<span data-ttu-id="e2d90-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e2d90-118">Data Item Type</span></span>|<span data-ttu-id="e2d90-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2d90-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e2d90-120">Eccezione</span><span class="sxs-lookup"><span data-stu-id="e2d90-120">Exception</span></span>|<span data-ttu-id="e2d90-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2d90-121">xs:string</span></span>|<span data-ttu-id="e2d90-122">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e2d90-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="e2d90-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e2d90-123">AppDomain</span></span>|<span data-ttu-id="e2d90-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2d90-124">xs:string</span></span>|<span data-ttu-id="e2d90-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e2d90-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
