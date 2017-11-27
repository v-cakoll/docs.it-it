---
title: 1018 - StartCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f74a133a685699bcefc014269a9ecb3ebea4e505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="0293e-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0293e-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0293e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0293e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0293e-104">ID</span><span class="sxs-lookup"><span data-stu-id="0293e-104">ID</span></span>|<span data-ttu-id="0293e-105">1018</span><span class="sxs-lookup"><span data-stu-id="0293e-105">1018</span></span>|  
|<span data-ttu-id="0293e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0293e-106">Keywords</span></span>|<span data-ttu-id="0293e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0293e-107">WFRuntime</span></span>|  
|<span data-ttu-id="0293e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0293e-108">Level</span></span>|<span data-ttu-id="0293e-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="0293e-109">Verbose</span></span>|  
|<span data-ttu-id="0293e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0293e-110">Channel</span></span>|<span data-ttu-id="0293e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0293e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0293e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0293e-112">Description</span></span>  
 <span data-ttu-id="0293e-113">Indica che viene avviata l'esecuzione di CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0293e-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0293e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0293e-114">Message</span></span>  
 <span data-ttu-id="0293e-115">Avvio dell'esecuzione di CancelActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0293e-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0293e-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0293e-116">Details</span></span>  
  
|<span data-ttu-id="0293e-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0293e-117">Data Item Name</span></span>|<span data-ttu-id="0293e-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0293e-118">Data Item Type</span></span>|<span data-ttu-id="0293e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0293e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0293e-120">Attività</span><span class="sxs-lookup"><span data-stu-id="0293e-120">Activity</span></span>|<span data-ttu-id="0293e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0293e-121">xs:string</span></span>|<span data-ttu-id="0293e-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="0293e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0293e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0293e-123">DisplayName</span></span>|<span data-ttu-id="0293e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0293e-124">xs:string</span></span>|<span data-ttu-id="0293e-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0293e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0293e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0293e-126">InstanceId</span></span>|<span data-ttu-id="0293e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0293e-127">xs:string</span></span>|<span data-ttu-id="0293e-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0293e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0293e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0293e-129">AppDomain</span></span>|<span data-ttu-id="0293e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0293e-130">xs:string</span></span>|<span data-ttu-id="0293e-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0293e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
