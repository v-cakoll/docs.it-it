---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ba5e4aa8e1338321838e40db7d976107315ef64
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="6d17a-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="6d17a-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="6d17a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6d17a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d17a-104">ID</span><span class="sxs-lookup"><span data-stu-id="6d17a-104">ID</span></span>|<span data-ttu-id="6d17a-105">3552</span><span class="sxs-lookup"><span data-stu-id="6d17a-105">3552</span></span>|  
|<span data-ttu-id="6d17a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6d17a-106">Keywords</span></span>|<span data-ttu-id="6d17a-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="6d17a-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="6d17a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6d17a-108">Level</span></span>|<span data-ttu-id="6d17a-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="6d17a-109">Warning</span></span>|  
|<span data-ttu-id="6d17a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6d17a-110">Channel</span></span>|<span data-ttu-id="6d17a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6d17a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d17a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d17a-112">Description</span></span>  
 <span data-ttu-id="6d17a-113">Indica che è stato raggiunto il limite per la velocità 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="6d17a-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d17a-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6d17a-114">Message</span></span>  
 <span data-ttu-id="6d17a-115">È stato raggiunto il limite velocità 'MaxPendingMessagesPerChannel' di '%1'.</span><span class="sxs-lookup"><span data-stu-id="6d17a-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="6d17a-116">Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="6d17a-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d17a-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6d17a-117">Details</span></span>  
  
|<span data-ttu-id="6d17a-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6d17a-118">Data Item Name</span></span>|<span data-ttu-id="6d17a-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6d17a-119">Data Item Type</span></span>|<span data-ttu-id="6d17a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d17a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d17a-121">Limit</span><span class="sxs-lookup"><span data-stu-id="6d17a-121">Limit</span></span>|<span data-ttu-id="6d17a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d17a-122">xs:string</span></span>|<span data-ttu-id="6d17a-123">È stato raggiunto il limite per la velocità MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="6d17a-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="6d17a-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d17a-124">AppDomain</span></span>|<span data-ttu-id="6d17a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d17a-125">xs:string</span></span>|<span data-ttu-id="6d17a-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6d17a-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
