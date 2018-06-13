---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514482"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="096e9-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="096e9-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="096e9-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="096e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="096e9-104">ID</span><span class="sxs-lookup"><span data-stu-id="096e9-104">ID</span></span>|<span data-ttu-id="096e9-105">39458</span><span class="sxs-lookup"><span data-stu-id="096e9-105">39458</span></span>|  
|<span data-ttu-id="096e9-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="096e9-106">Keywords</span></span>|<span data-ttu-id="096e9-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="096e9-107">WFTracking</span></span>|  
|<span data-ttu-id="096e9-108">Livello</span><span class="sxs-lookup"><span data-stu-id="096e9-108">Level</span></span>|<span data-ttu-id="096e9-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="096e9-109">Warning</span></span>|  
|<span data-ttu-id="096e9-110">Canale</span><span class="sxs-lookup"><span data-stu-id="096e9-110">Channel</span></span>|<span data-ttu-id="096e9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="096e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="096e9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="096e9-112">Description</span></span>  
 <span data-ttu-id="096e9-113">Indica che un record di rilevamento è stato troncato.</span><span class="sxs-lookup"><span data-stu-id="096e9-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="096e9-114">Variabili/annotazioni/dati utente rimossi.</span><span class="sxs-lookup"><span data-stu-id="096e9-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="096e9-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="096e9-115">Message</span></span>  
 <span data-ttu-id="096e9-116">Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2.</span><span class="sxs-lookup"><span data-stu-id="096e9-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="096e9-117">Variabili/annotazioni/dati utente rimossi</span><span class="sxs-lookup"><span data-stu-id="096e9-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="096e9-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="096e9-118">Details</span></span>  
  
|<span data-ttu-id="096e9-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="096e9-119">Data Item Name</span></span>|<span data-ttu-id="096e9-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="096e9-120">Data Item Type</span></span>|<span data-ttu-id="096e9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="096e9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="096e9-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="096e9-122">RecordNumber</span></span>|<span data-ttu-id="096e9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="096e9-123">xs:string</span></span>|<span data-ttu-id="096e9-124">Numero del record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="096e9-124">The tracking record number.</span></span>|  
|<span data-ttu-id="096e9-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="096e9-125">ProviderId</span></span>|<span data-ttu-id="096e9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="096e9-126">xs:string</span></span>|<span data-ttu-id="096e9-127">ID del provider ETW.</span><span class="sxs-lookup"><span data-stu-id="096e9-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="096e9-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="096e9-128">AppDomain</span></span>|<span data-ttu-id="096e9-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="096e9-129">xs:string</span></span>|<span data-ttu-id="096e9-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="096e9-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
