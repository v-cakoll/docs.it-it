---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06d4695eb125475f41a94c7f2266df6d2c3f400d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="24075-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="24075-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="24075-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="24075-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24075-104">ID</span><span class="sxs-lookup"><span data-stu-id="24075-104">ID</span></span>|<span data-ttu-id="24075-105">4203</span><span class="sxs-lookup"><span data-stu-id="24075-105">4203</span></span>|  
|<span data-ttu-id="24075-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="24075-106">Keywords</span></span>|<span data-ttu-id="24075-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="24075-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="24075-108">Livello</span><span class="sxs-lookup"><span data-stu-id="24075-108">Level</span></span>|<span data-ttu-id="24075-109">Errore</span><span class="sxs-lookup"><span data-stu-id="24075-109">Error</span></span>|  
|<span data-ttu-id="24075-110">Canale</span><span class="sxs-lookup"><span data-stu-id="24075-110">Channel</span></span>|<span data-ttu-id="24075-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="24075-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="24075-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24075-112">Description</span></span>  
 <span data-ttu-id="24075-113">Indica che il provider SQL non è in grado di estendere la scadenza del blocco perché la scadenza è già passata o il proprietario del blocco è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="24075-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="24075-114">SqlWorkflowInstanceStore verrà interrotto.</span><span class="sxs-lookup"><span data-stu-id="24075-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="24075-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="24075-115">Message</span></span>  
 <span data-ttu-id="24075-116">Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato.</span><span class="sxs-lookup"><span data-stu-id="24075-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="24075-117">Interruzione di SqlWorkflowInstanceStore in corso.</span><span class="sxs-lookup"><span data-stu-id="24075-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="24075-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="24075-118">Details</span></span>  
  
|<span data-ttu-id="24075-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="24075-119">Data Item Name</span></span>|<span data-ttu-id="24075-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="24075-120">Data Item Type</span></span>|<span data-ttu-id="24075-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24075-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="24075-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="24075-122">AppDomain</span></span>|<span data-ttu-id="24075-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="24075-123">xs:string</span></span>|<span data-ttu-id="24075-124">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="24075-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
