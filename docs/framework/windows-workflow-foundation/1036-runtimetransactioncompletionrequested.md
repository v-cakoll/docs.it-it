---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f497d777221a98b38603b2ced29342651b1020b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="85bc2-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="85bc2-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="85bc2-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="85bc2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85bc2-104">ID</span><span class="sxs-lookup"><span data-stu-id="85bc2-104">ID</span></span>|<span data-ttu-id="85bc2-105">1036</span><span class="sxs-lookup"><span data-stu-id="85bc2-105">1036</span></span>|  
|<span data-ttu-id="85bc2-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="85bc2-106">Keywords</span></span>|<span data-ttu-id="85bc2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="85bc2-107">WFRuntime</span></span>|  
|<span data-ttu-id="85bc2-108">Livello</span><span class="sxs-lookup"><span data-stu-id="85bc2-108">Level</span></span>|<span data-ttu-id="85bc2-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="85bc2-109">Verbose</span></span>|  
|<span data-ttu-id="85bc2-110">Canale</span><span class="sxs-lookup"><span data-stu-id="85bc2-110">Channel</span></span>|<span data-ttu-id="85bc2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="85bc2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="85bc2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85bc2-112">Description</span></span>  
 <span data-ttu-id="85bc2-113">Indica che un'attività ha pianificato il completamento della transazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="85bc2-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="85bc2-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="85bc2-114">Message</span></span>  
 <span data-ttu-id="85bc2-115">L'attività '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato il completamento della transazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="85bc2-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="85bc2-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="85bc2-116">Details</span></span>  
  
|<span data-ttu-id="85bc2-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="85bc2-117">Data Item Name</span></span>|<span data-ttu-id="85bc2-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="85bc2-118">Data Item Type</span></span>|<span data-ttu-id="85bc2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85bc2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="85bc2-120">Attività</span><span class="sxs-lookup"><span data-stu-id="85bc2-120">Activity</span></span>|<span data-ttu-id="85bc2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="85bc2-121">xs:string</span></span>|<span data-ttu-id="85bc2-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="85bc2-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="85bc2-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="85bc2-123">DisplayName</span></span>|<span data-ttu-id="85bc2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="85bc2-124">xs:string</span></span>|<span data-ttu-id="85bc2-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="85bc2-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="85bc2-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="85bc2-126">InstanceId</span></span>|<span data-ttu-id="85bc2-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="85bc2-127">xs:string</span></span>|<span data-ttu-id="85bc2-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="85bc2-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="85bc2-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="85bc2-129">AppDomain</span></span>|<span data-ttu-id="85bc2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="85bc2-130">xs:string</span></span>|<span data-ttu-id="85bc2-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="85bc2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
