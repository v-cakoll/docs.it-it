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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ffd44cf9d2333b22e3be809d05f2fa8c33d4cac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="fa68d-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="fa68d-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="fa68d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fa68d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa68d-104">ID</span><span class="sxs-lookup"><span data-stu-id="fa68d-104">ID</span></span>|<span data-ttu-id="fa68d-105">4211</span><span class="sxs-lookup"><span data-stu-id="fa68d-105">4211</span></span>|  
|<span data-ttu-id="fa68d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fa68d-106">Keywords</span></span>|<span data-ttu-id="fa68d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="fa68d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="fa68d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="fa68d-108">Level</span></span>|<span data-ttu-id="fa68d-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="fa68d-109">Warning</span></span>|  
|<span data-ttu-id="fa68d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="fa68d-110">Channel</span></span>|<span data-ttu-id="fa68d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fa68d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fa68d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa68d-112">Description</span></span>  
 <span data-ttu-id="fa68d-113">Indica l'accodamento di nuovi tentativi di SQL.</span><span class="sxs-lookup"><span data-stu-id="fa68d-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fa68d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fa68d-114">Message</span></span>  
 <span data-ttu-id="fa68d-115">Accodamento nuovi tentativi di SQL con ritardo di %1 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="fa68d-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fa68d-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fa68d-116">Details</span></span>  
  
|<span data-ttu-id="fa68d-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="fa68d-117">Data Item Name</span></span>|<span data-ttu-id="fa68d-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="fa68d-118">Data Item Type</span></span>|<span data-ttu-id="fa68d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa68d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fa68d-120">Delay</span><span class="sxs-lookup"><span data-stu-id="fa68d-120">Delay</span></span>|<span data-ttu-id="fa68d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa68d-121">xs:string</span></span>|<span data-ttu-id="fa68d-122">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="fa68d-122">The delay between retries.</span></span>|  
|<span data-ttu-id="fa68d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa68d-123">AppDomain</span></span>|<span data-ttu-id="fa68d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa68d-124">xs:string</span></span>|<span data-ttu-id="fa68d-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fa68d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
