---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d881f1be4e809cf45f100b966d6013ae8fa88f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="212db-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="212db-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="212db-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="212db-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="212db-104">ID</span><span class="sxs-lookup"><span data-stu-id="212db-104">ID</span></span>|<span data-ttu-id="212db-105">1026</span><span class="sxs-lookup"><span data-stu-id="212db-105">1026</span></span>|  
|<span data-ttu-id="212db-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="212db-106">Keywords</span></span>|<span data-ttu-id="212db-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="212db-107">WFRuntime</span></span>|  
|<span data-ttu-id="212db-108">Livello</span><span class="sxs-lookup"><span data-stu-id="212db-108">Level</span></span>|<span data-ttu-id="212db-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="212db-109">Verbose</span></span>|  
|<span data-ttu-id="212db-110">Canale</span><span class="sxs-lookup"><span data-stu-id="212db-110">Channel</span></span>|<span data-ttu-id="212db-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="212db-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="212db-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="212db-112">Description</span></span>  
 <span data-ttu-id="212db-113">Indica che un elemento TransactionContextWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="212db-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="212db-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="212db-114">Message</span></span>  
 <span data-ttu-id="212db-115">TransactionContextWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="212db-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="212db-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="212db-116">Details</span></span>  
  
|<span data-ttu-id="212db-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="212db-117">Data Item Name</span></span>|<span data-ttu-id="212db-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="212db-118">Data Item Type</span></span>|<span data-ttu-id="212db-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="212db-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="212db-120">Attività</span><span class="sxs-lookup"><span data-stu-id="212db-120">Activity</span></span>|<span data-ttu-id="212db-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="212db-121">xs:string</span></span>|<span data-ttu-id="212db-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="212db-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="212db-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="212db-123">DisplayName</span></span>|<span data-ttu-id="212db-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="212db-124">xs:string</span></span>|<span data-ttu-id="212db-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="212db-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="212db-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="212db-126">InstanceId</span></span>|<span data-ttu-id="212db-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="212db-127">xs:string</span></span>|<span data-ttu-id="212db-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="212db-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="212db-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="212db-129">AppDomain</span></span>|<span data-ttu-id="212db-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="212db-130">xs:string</span></span>|<span data-ttu-id="212db-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="212db-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
