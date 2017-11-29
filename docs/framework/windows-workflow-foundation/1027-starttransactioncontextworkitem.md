---
title: 1027 - StartTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be35a4d478f4f2af0921cac942ebb95d6aed38d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="51d09-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="51d09-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="51d09-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="51d09-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51d09-104">ID</span><span class="sxs-lookup"><span data-stu-id="51d09-104">ID</span></span>|<span data-ttu-id="51d09-105">1027</span><span class="sxs-lookup"><span data-stu-id="51d09-105">1027</span></span>|  
|<span data-ttu-id="51d09-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51d09-106">Keywords</span></span>|<span data-ttu-id="51d09-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="51d09-107">WFRuntime</span></span>|  
|<span data-ttu-id="51d09-108">Livello</span><span class="sxs-lookup"><span data-stu-id="51d09-108">Level</span></span>|<span data-ttu-id="51d09-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="51d09-109">Verbose</span></span>|  
|<span data-ttu-id="51d09-110">Canale</span><span class="sxs-lookup"><span data-stu-id="51d09-110">Channel</span></span>|<span data-ttu-id="51d09-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="51d09-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="51d09-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d09-112">Description</span></span>  
 <span data-ttu-id="51d09-113">Indica che viene avviata l'esecuzione di TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="51d09-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="51d09-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="51d09-114">Message</span></span>  
 <span data-ttu-id="51d09-115">Avvio dell'esecuzione di TransactionContextWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="51d09-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="51d09-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="51d09-116">Details</span></span>  
  
|<span data-ttu-id="51d09-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="51d09-117">Data Item Name</span></span>|<span data-ttu-id="51d09-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="51d09-118">Data Item Type</span></span>|<span data-ttu-id="51d09-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51d09-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="51d09-120">Attività</span><span class="sxs-lookup"><span data-stu-id="51d09-120">Activity</span></span>|<span data-ttu-id="51d09-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="51d09-121">xs:string</span></span>|<span data-ttu-id="51d09-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="51d09-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="51d09-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="51d09-123">DisplayName</span></span>|<span data-ttu-id="51d09-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="51d09-124">xs:string</span></span>|<span data-ttu-id="51d09-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="51d09-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="51d09-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="51d09-126">InstanceId</span></span>|<span data-ttu-id="51d09-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="51d09-127">xs:string</span></span>|<span data-ttu-id="51d09-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="51d09-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="51d09-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="51d09-129">AppDomain</span></span>|<span data-ttu-id="51d09-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="51d09-130">xs:string</span></span>|<span data-ttu-id="51d09-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="51d09-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
