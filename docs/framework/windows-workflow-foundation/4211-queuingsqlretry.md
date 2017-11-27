---
title: 4211 - QueuingSqlRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c318ee6509ce8b96a1e7e78a13f4aeb7c76dde6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="616ca-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="616ca-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="616ca-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="616ca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="616ca-104">ID</span><span class="sxs-lookup"><span data-stu-id="616ca-104">ID</span></span>|<span data-ttu-id="616ca-105">4211</span><span class="sxs-lookup"><span data-stu-id="616ca-105">4211</span></span>|  
|<span data-ttu-id="616ca-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="616ca-106">Keywords</span></span>|<span data-ttu-id="616ca-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="616ca-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="616ca-108">Livello</span><span class="sxs-lookup"><span data-stu-id="616ca-108">Level</span></span>|<span data-ttu-id="616ca-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="616ca-109">Warning</span></span>|  
|<span data-ttu-id="616ca-110">Canale</span><span class="sxs-lookup"><span data-stu-id="616ca-110">Channel</span></span>|<span data-ttu-id="616ca-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="616ca-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="616ca-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616ca-112">Description</span></span>  
 <span data-ttu-id="616ca-113">Indica l'accodamento di nuovi tentativi di SQL.</span><span class="sxs-lookup"><span data-stu-id="616ca-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="616ca-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="616ca-114">Message</span></span>  
 <span data-ttu-id="616ca-115">Accodamento nuovi tentativi di SQL con ritardo di %1 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="616ca-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="616ca-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="616ca-116">Details</span></span>  
  
|<span data-ttu-id="616ca-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="616ca-117">Data Item Name</span></span>|<span data-ttu-id="616ca-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="616ca-118">Data Item Type</span></span>|<span data-ttu-id="616ca-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="616ca-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="616ca-120">Delay</span><span class="sxs-lookup"><span data-stu-id="616ca-120">Delay</span></span>|<span data-ttu-id="616ca-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="616ca-121">xs:string</span></span>|<span data-ttu-id="616ca-122">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="616ca-122">The delay between retries.</span></span>|  
|<span data-ttu-id="616ca-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="616ca-123">AppDomain</span></span>|<span data-ttu-id="616ca-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="616ca-124">xs:string</span></span>|<span data-ttu-id="616ca-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="616ca-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
