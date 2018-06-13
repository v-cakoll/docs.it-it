---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514569"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="80232-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="80232-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="80232-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="80232-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80232-104">ID</span><span class="sxs-lookup"><span data-stu-id="80232-104">ID</span></span>|<span data-ttu-id="80232-105">4211</span><span class="sxs-lookup"><span data-stu-id="80232-105">4211</span></span>|  
|<span data-ttu-id="80232-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="80232-106">Keywords</span></span>|<span data-ttu-id="80232-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="80232-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="80232-108">Livello</span><span class="sxs-lookup"><span data-stu-id="80232-108">Level</span></span>|<span data-ttu-id="80232-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="80232-109">Warning</span></span>|  
|<span data-ttu-id="80232-110">Canale</span><span class="sxs-lookup"><span data-stu-id="80232-110">Channel</span></span>|<span data-ttu-id="80232-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="80232-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="80232-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80232-112">Description</span></span>  
 <span data-ttu-id="80232-113">Indica l'accodamento di nuovi tentativi di SQL.</span><span class="sxs-lookup"><span data-stu-id="80232-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="80232-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="80232-114">Message</span></span>  
 <span data-ttu-id="80232-115">Accodamento nuovi tentativi di SQL con ritardo di %1 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="80232-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="80232-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="80232-116">Details</span></span>  
  
|<span data-ttu-id="80232-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="80232-117">Data Item Name</span></span>|<span data-ttu-id="80232-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="80232-118">Data Item Type</span></span>|<span data-ttu-id="80232-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80232-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="80232-120">Delay</span><span class="sxs-lookup"><span data-stu-id="80232-120">Delay</span></span>|<span data-ttu-id="80232-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="80232-121">xs:string</span></span>|<span data-ttu-id="80232-122">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="80232-122">The delay between retries.</span></span>|  
|<span data-ttu-id="80232-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="80232-123">AppDomain</span></span>|<span data-ttu-id="80232-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="80232-124">xs:string</span></span>|<span data-ttu-id="80232-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="80232-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
