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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 300e843529bfc76df4193b46cd713ce0bd9cdbfd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="1c544-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="1c544-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="1c544-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1c544-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c544-104">ID</span><span class="sxs-lookup"><span data-stu-id="1c544-104">ID</span></span>|<span data-ttu-id="1c544-105">1132</span><span class="sxs-lookup"><span data-stu-id="1c544-105">1132</span></span>|  
|<span data-ttu-id="1c544-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c544-106">Keywords</span></span>|<span data-ttu-id="1c544-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1c544-107">WFRuntime</span></span>|  
|<span data-ttu-id="1c544-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1c544-108">Level</span></span>|<span data-ttu-id="1c544-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="1c544-109">Information</span></span>|  
|<span data-ttu-id="1c544-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1c544-110">Channel</span></span>|<span data-ttu-id="1c544-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1c544-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1c544-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c544-112">Description</span></span>  
 <span data-ttu-id="1c544-113">Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che non viene usato il modello asincrono quando viene richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="1c544-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1c544-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1c544-114">Message</span></span>  
 <span data-ttu-id="1c544-115">InvokeMethod '%1': il metodo non usa un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="1c544-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1c544-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1c544-116">Details</span></span>  
  
|<span data-ttu-id="1c544-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1c544-117">Data Item Name</span></span>|<span data-ttu-id="1c544-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1c544-118">Data Item Type</span></span>|<span data-ttu-id="1c544-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c544-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1c544-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="1c544-120">InvokeMethod</span></span>|<span data-ttu-id="1c544-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c544-121">xs:string</span></span>|<span data-ttu-id="1c544-122">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="1c544-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="1c544-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1c544-123">AppDomain</span></span>|<span data-ttu-id="1c544-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c544-124">xs:string</span></span>|<span data-ttu-id="1c544-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1c544-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
