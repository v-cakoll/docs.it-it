---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512666"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="79e20-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="79e20-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="79e20-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="79e20-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79e20-104">ID</span><span class="sxs-lookup"><span data-stu-id="79e20-104">ID</span></span>|<span data-ttu-id="79e20-105">1131</span><span class="sxs-lookup"><span data-stu-id="79e20-105">1131</span></span>|  
|<span data-ttu-id="79e20-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="79e20-106">Keywords</span></span>|<span data-ttu-id="79e20-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="79e20-107">WFRuntime</span></span>|  
|<span data-ttu-id="79e20-108">Livello</span><span class="sxs-lookup"><span data-stu-id="79e20-108">Level</span></span>|<span data-ttu-id="79e20-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="79e20-109">Information</span></span>|  
|<span data-ttu-id="79e20-110">Canale</span><span class="sxs-lookup"><span data-stu-id="79e20-110">Channel</span></span>|<span data-ttu-id="79e20-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="79e20-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="79e20-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79e20-112">Description</span></span>  
 <span data-ttu-id="79e20-113">Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che viene usato il modello asincrono quando viene richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="79e20-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="79e20-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="79e20-114">Message</span></span>  
 <span data-ttu-id="79e20-115">InvokeMethod '%1': il metodo usa un modello asincrono di '%2' e '%3'.</span><span class="sxs-lookup"><span data-stu-id="79e20-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="79e20-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="79e20-116">Details</span></span>  
  
|<span data-ttu-id="79e20-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="79e20-117">Data Item Name</span></span>|<span data-ttu-id="79e20-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="79e20-118">Data Item Type</span></span>|<span data-ttu-id="79e20-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79e20-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="79e20-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="79e20-120">InvokeMethod</span></span>|<span data-ttu-id="79e20-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="79e20-121">xs:string</span></span>|<span data-ttu-id="79e20-122">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="79e20-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="79e20-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="79e20-123">BeginMethod</span></span>|<span data-ttu-id="79e20-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="79e20-124">xs:string</span></span>|<span data-ttu-id="79e20-125">Nome del metodo Begin.</span><span class="sxs-lookup"><span data-stu-id="79e20-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="79e20-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="79e20-126">EndMethod</span></span>|<span data-ttu-id="79e20-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="79e20-127">xs:string</span></span>|<span data-ttu-id="79e20-128">Nome del metodo End.</span><span class="sxs-lookup"><span data-stu-id="79e20-128">The name of the end method.</span></span>|  
|<span data-ttu-id="79e20-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="79e20-129">AppDomain</span></span>|<span data-ttu-id="79e20-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="79e20-130">xs:string</span></span>|<span data-ttu-id="79e20-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="79e20-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
