---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 739357df85ceb73e246adcb2b09f88d270d853ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="1864e-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="1864e-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="1864e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1864e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1864e-104">ID</span><span class="sxs-lookup"><span data-stu-id="1864e-104">ID</span></span>|<span data-ttu-id="1864e-105">1131</span><span class="sxs-lookup"><span data-stu-id="1864e-105">1131</span></span>|  
|<span data-ttu-id="1864e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1864e-106">Keywords</span></span>|<span data-ttu-id="1864e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1864e-107">WFRuntime</span></span>|  
|<span data-ttu-id="1864e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1864e-108">Level</span></span>|<span data-ttu-id="1864e-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="1864e-109">Information</span></span>|  
|<span data-ttu-id="1864e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1864e-110">Channel</span></span>|<span data-ttu-id="1864e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1864e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1864e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1864e-112">Description</span></span>  
 <span data-ttu-id="1864e-113">Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che viene usato il modello asincrono quando viene richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="1864e-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1864e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1864e-114">Message</span></span>  
 <span data-ttu-id="1864e-115">InvokeMethod '%1': il metodo usa un modello asincrono di '%2' e '%3'.</span><span class="sxs-lookup"><span data-stu-id="1864e-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1864e-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1864e-116">Details</span></span>  
  
|<span data-ttu-id="1864e-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1864e-117">Data Item Name</span></span>|<span data-ttu-id="1864e-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1864e-118">Data Item Type</span></span>|<span data-ttu-id="1864e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1864e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1864e-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="1864e-120">InvokeMethod</span></span>|<span data-ttu-id="1864e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1864e-121">xs:string</span></span>|<span data-ttu-id="1864e-122">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="1864e-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="1864e-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="1864e-123">BeginMethod</span></span>|<span data-ttu-id="1864e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1864e-124">xs:string</span></span>|<span data-ttu-id="1864e-125">Nome del metodo Begin.</span><span class="sxs-lookup"><span data-stu-id="1864e-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="1864e-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="1864e-126">EndMethod</span></span>|<span data-ttu-id="1864e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1864e-127">xs:string</span></span>|<span data-ttu-id="1864e-128">Nome del metodo End.</span><span class="sxs-lookup"><span data-stu-id="1864e-128">The name of the end method.</span></span>|  
|<span data-ttu-id="1864e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1864e-129">AppDomain</span></span>|<span data-ttu-id="1864e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1864e-130">xs:string</span></span>|<span data-ttu-id="1864e-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1864e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
