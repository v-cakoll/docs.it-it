---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75386b56f7926b9ddb883e0ca212d795898fe6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="b981b-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="b981b-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="b981b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b981b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b981b-104">ID</span><span class="sxs-lookup"><span data-stu-id="b981b-104">ID</span></span>|<span data-ttu-id="b981b-105">1132</span><span class="sxs-lookup"><span data-stu-id="b981b-105">1132</span></span>|  
|<span data-ttu-id="b981b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b981b-106">Keywords</span></span>|<span data-ttu-id="b981b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b981b-107">WFRuntime</span></span>|  
|<span data-ttu-id="b981b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b981b-108">Level</span></span>|<span data-ttu-id="b981b-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="b981b-109">Information</span></span>|  
|<span data-ttu-id="b981b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b981b-110">Channel</span></span>|<span data-ttu-id="b981b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b981b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b981b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b981b-112">Description</span></span>  
 <span data-ttu-id="b981b-113">Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che non viene usato il modello asincrono quando viene richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="b981b-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b981b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b981b-114">Message</span></span>  
 <span data-ttu-id="b981b-115">InvokeMethod '%1': il metodo non usa un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="b981b-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b981b-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b981b-116">Details</span></span>  
  
|<span data-ttu-id="b981b-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b981b-117">Data Item Name</span></span>|<span data-ttu-id="b981b-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b981b-118">Data Item Type</span></span>|<span data-ttu-id="b981b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b981b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b981b-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b981b-120">InvokeMethod</span></span>|<span data-ttu-id="b981b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b981b-121">xs:string</span></span>|<span data-ttu-id="b981b-122">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="b981b-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="b981b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b981b-123">AppDomain</span></span>|<span data-ttu-id="b981b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b981b-124">xs:string</span></span>|<span data-ttu-id="b981b-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b981b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
