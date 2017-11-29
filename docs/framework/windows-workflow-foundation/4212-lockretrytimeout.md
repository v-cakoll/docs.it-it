---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 897e6ef8b739654a61058106966c870c47f8129a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="b6ca2-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="b6ca2-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="b6ca2-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b6ca2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6ca2-104">ID</span><span class="sxs-lookup"><span data-stu-id="b6ca2-104">ID</span></span>|<span data-ttu-id="b6ca2-105">4212</span><span class="sxs-lookup"><span data-stu-id="b6ca2-105">4212</span></span>|  
|<span data-ttu-id="b6ca2-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b6ca2-106">Keywords</span></span>|<span data-ttu-id="b6ca2-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b6ca2-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b6ca2-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b6ca2-108">Level</span></span>|<span data-ttu-id="b6ca2-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="b6ca2-109">Warning</span></span>|  
|<span data-ttu-id="b6ca2-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b6ca2-110">Channel</span></span>|<span data-ttu-id="b6ca2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b6ca2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6ca2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6ca2-112">Description</span></span>  
 <span data-ttu-id="b6ca2-113">Timeout rilevato del provider SQL durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6ca2-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b6ca2-114">Message</span></span>  
 <span data-ttu-id="b6ca2-115">Timeout durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="b6ca2-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="b6ca2-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6ca2-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b6ca2-118">Details</span></span>  
  
|<span data-ttu-id="b6ca2-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b6ca2-119">Data Item Name</span></span>|<span data-ttu-id="b6ca2-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b6ca2-120">Data Item Type</span></span>|<span data-ttu-id="b6ca2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6ca2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6ca2-122">Delay</span><span class="sxs-lookup"><span data-stu-id="b6ca2-122">Delay</span></span>|<span data-ttu-id="b6ca2-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6ca2-123">xs:string</span></span>|<span data-ttu-id="b6ca2-124">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-124">The delay between retries.</span></span>|  
|<span data-ttu-id="b6ca2-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6ca2-125">AppDomain</span></span>|<span data-ttu-id="b6ca2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6ca2-126">xs:string</span></span>|<span data-ttu-id="b6ca2-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
