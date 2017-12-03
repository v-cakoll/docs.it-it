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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6545159012519e2943556b093a0a0bfc3e535217
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="ccac1-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="ccac1-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ccac1-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ccac1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccac1-104">ID</span><span class="sxs-lookup"><span data-stu-id="ccac1-104">ID</span></span>|<span data-ttu-id="ccac1-105">1027</span><span class="sxs-lookup"><span data-stu-id="ccac1-105">1027</span></span>|  
|<span data-ttu-id="ccac1-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ccac1-106">Keywords</span></span>|<span data-ttu-id="ccac1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ccac1-107">WFRuntime</span></span>|  
|<span data-ttu-id="ccac1-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ccac1-108">Level</span></span>|<span data-ttu-id="ccac1-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="ccac1-109">Verbose</span></span>|  
|<span data-ttu-id="ccac1-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ccac1-110">Channel</span></span>|<span data-ttu-id="ccac1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ccac1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ccac1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccac1-112">Description</span></span>  
 <span data-ttu-id="ccac1-113">Indica che viene avviata l'esecuzione di TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ccac1-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ccac1-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ccac1-114">Message</span></span>  
 <span data-ttu-id="ccac1-115">Avvio dell'esecuzione di TransactionContextWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ccac1-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ccac1-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ccac1-116">Details</span></span>  
  
|<span data-ttu-id="ccac1-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ccac1-117">Data Item Name</span></span>|<span data-ttu-id="ccac1-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ccac1-118">Data Item Type</span></span>|<span data-ttu-id="ccac1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccac1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ccac1-120">Attività</span><span class="sxs-lookup"><span data-stu-id="ccac1-120">Activity</span></span>|<span data-ttu-id="ccac1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ccac1-121">xs:string</span></span>|<span data-ttu-id="ccac1-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="ccac1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ccac1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ccac1-123">DisplayName</span></span>|<span data-ttu-id="ccac1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ccac1-124">xs:string</span></span>|<span data-ttu-id="ccac1-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ccac1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ccac1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ccac1-126">InstanceId</span></span>|<span data-ttu-id="ccac1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ccac1-127">xs:string</span></span>|<span data-ttu-id="ccac1-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ccac1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ccac1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ccac1-129">AppDomain</span></span>|<span data-ttu-id="ccac1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ccac1-130">xs:string</span></span>|<span data-ttu-id="ccac1-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ccac1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
