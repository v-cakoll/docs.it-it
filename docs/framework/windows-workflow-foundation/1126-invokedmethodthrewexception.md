---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b11c2f167ce7afce992cddb2f32f840212d4ac8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="160cb-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="160cb-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="160cb-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="160cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="160cb-104">ID</span><span class="sxs-lookup"><span data-stu-id="160cb-104">ID</span></span>|<span data-ttu-id="160cb-105">1126</span><span class="sxs-lookup"><span data-stu-id="160cb-105">1126</span></span>|  
|<span data-ttu-id="160cb-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="160cb-106">Keywords</span></span>|<span data-ttu-id="160cb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="160cb-107">WFRuntime</span></span>|  
|<span data-ttu-id="160cb-108">Livello</span><span class="sxs-lookup"><span data-stu-id="160cb-108">Level</span></span>|<span data-ttu-id="160cb-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="160cb-109">Information</span></span>|  
|<span data-ttu-id="160cb-110">Canale</span><span class="sxs-lookup"><span data-stu-id="160cb-110">Channel</span></span>|<span data-ttu-id="160cb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="160cb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="160cb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="160cb-112">Description</span></span>  
 <span data-ttu-id="160cb-113">Indica che è stata generata un'eccezione dal metodo chiamato dall'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="160cb-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="160cb-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="160cb-114">Message</span></span>  
 <span data-ttu-id="160cb-115">È stata generata un'eccezione nel metodo chiamato dall'attività '%1'.</span><span class="sxs-lookup"><span data-stu-id="160cb-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="160cb-116">%2</span><span class="sxs-lookup"><span data-stu-id="160cb-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="160cb-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="160cb-117">Details</span></span>  
  
|<span data-ttu-id="160cb-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="160cb-118">Data Item Name</span></span>|<span data-ttu-id="160cb-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="160cb-119">Data Item Type</span></span>|<span data-ttu-id="160cb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="160cb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="160cb-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="160cb-121">InvokeMethod</span></span>|<span data-ttu-id="160cb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="160cb-122">xs:string</span></span>|<span data-ttu-id="160cb-123">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="160cb-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="160cb-124">Eccezione</span><span class="sxs-lookup"><span data-stu-id="160cb-124">Exception</span></span>|<span data-ttu-id="160cb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="160cb-125">xs:string</span></span>|<span data-ttu-id="160cb-126">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="160cb-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="160cb-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="160cb-127">AppDomain</span></span>|<span data-ttu-id="160cb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="160cb-128">xs:string</span></span>|<span data-ttu-id="160cb-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="160cb-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
