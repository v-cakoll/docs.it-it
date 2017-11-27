---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc60af91088fd61910dc0301b93844f4771177af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="fe114-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="fe114-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fe114-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fe114-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe114-104">ID</span><span class="sxs-lookup"><span data-stu-id="fe114-104">ID</span></span>|<span data-ttu-id="fe114-105">1012</span><span class="sxs-lookup"><span data-stu-id="fe114-105">1012</span></span>|  
|<span data-ttu-id="fe114-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fe114-106">Keywords</span></span>|<span data-ttu-id="fe114-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fe114-107">WFRuntime</span></span>|  
|<span data-ttu-id="fe114-108">Livello</span><span class="sxs-lookup"><span data-stu-id="fe114-108">Level</span></span>|<span data-ttu-id="fe114-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="fe114-109">Verbose</span></span>|  
|<span data-ttu-id="fe114-110">Canale</span><span class="sxs-lookup"><span data-stu-id="fe114-110">Channel</span></span>|<span data-ttu-id="fe114-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fe114-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe114-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe114-112">Description</span></span>  
 <span data-ttu-id="fe114-113">Indica che viene avviata l'esecuzione di ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="fe114-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe114-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fe114-114">Message</span></span>  
 <span data-ttu-id="fe114-115">Avvio dell'esecuzione di ExecuteActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="fe114-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe114-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fe114-116">Details</span></span>  
  
|<span data-ttu-id="fe114-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="fe114-117">Data Item Name</span></span>|<span data-ttu-id="fe114-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="fe114-118">Data Item Type</span></span>|<span data-ttu-id="fe114-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe114-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe114-120">Attività</span><span class="sxs-lookup"><span data-stu-id="fe114-120">Activity</span></span>|<span data-ttu-id="fe114-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe114-121">xs:string</span></span>|<span data-ttu-id="fe114-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="fe114-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fe114-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fe114-123">DisplayName</span></span>|<span data-ttu-id="fe114-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe114-124">xs:string</span></span>|<span data-ttu-id="fe114-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="fe114-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fe114-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fe114-126">InstanceId</span></span>|<span data-ttu-id="fe114-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe114-127">xs:string</span></span>|<span data-ttu-id="fe114-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="fe114-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fe114-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe114-129">AppDomain</span></span>|<span data-ttu-id="fe114-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe114-130">xs:string</span></span>|<span data-ttu-id="fe114-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fe114-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
