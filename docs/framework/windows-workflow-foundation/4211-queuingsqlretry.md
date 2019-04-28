---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774244"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="3621b-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="3621b-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="3621b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3621b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3621b-104">Id</span><span class="sxs-lookup"><span data-stu-id="3621b-104">ID</span></span>|<span data-ttu-id="3621b-105">4211</span><span class="sxs-lookup"><span data-stu-id="3621b-105">4211</span></span>|  
|<span data-ttu-id="3621b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3621b-106">Keywords</span></span>|<span data-ttu-id="3621b-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3621b-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3621b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3621b-108">Level</span></span>|<span data-ttu-id="3621b-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="3621b-109">Warning</span></span>|  
|<span data-ttu-id="3621b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3621b-110">Channel</span></span>|<span data-ttu-id="3621b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3621b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3621b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3621b-112">Description</span></span>  
 <span data-ttu-id="3621b-113">Indica l'accodamento di nuovi tentativi di SQL.</span><span class="sxs-lookup"><span data-stu-id="3621b-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3621b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3621b-114">Message</span></span>  
 <span data-ttu-id="3621b-115">Accodamento nuovi tentativi di SQL con ritardo di %1 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="3621b-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3621b-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3621b-116">Details</span></span>  
  
|<span data-ttu-id="3621b-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3621b-117">Data Item Name</span></span>|<span data-ttu-id="3621b-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3621b-118">Data Item Type</span></span>|<span data-ttu-id="3621b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3621b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3621b-120">Ritardo</span><span class="sxs-lookup"><span data-stu-id="3621b-120">Delay</span></span>|<span data-ttu-id="3621b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3621b-121">xs:string</span></span>|<span data-ttu-id="3621b-122">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="3621b-122">The delay between retries.</span></span>|  
|<span data-ttu-id="3621b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3621b-123">AppDomain</span></span>|<span data-ttu-id="3621b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3621b-124">xs:string</span></span>|<span data-ttu-id="3621b-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3621b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
