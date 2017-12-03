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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5455472a5b9ebdba7aea7d0384ce9cd4a9a2849d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="457c6-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="457c6-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="457c6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="457c6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="457c6-104">ID</span><span class="sxs-lookup"><span data-stu-id="457c6-104">ID</span></span>|<span data-ttu-id="457c6-105">3552</span><span class="sxs-lookup"><span data-stu-id="457c6-105">3552</span></span>|  
|<span data-ttu-id="457c6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="457c6-106">Keywords</span></span>|<span data-ttu-id="457c6-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="457c6-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="457c6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="457c6-108">Level</span></span>|<span data-ttu-id="457c6-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="457c6-109">Warning</span></span>|  
|<span data-ttu-id="457c6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="457c6-110">Channel</span></span>|<span data-ttu-id="457c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="457c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="457c6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="457c6-112">Description</span></span>  
 <span data-ttu-id="457c6-113">Indica che è stato raggiunto il limite per la velocità 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="457c6-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="457c6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="457c6-114">Message</span></span>  
 <span data-ttu-id="457c6-115">È stato raggiunto il limite velocità 'MaxPendingMessagesPerChannel' di '%1'.</span><span class="sxs-lookup"><span data-stu-id="457c6-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="457c6-116">Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="457c6-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="457c6-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="457c6-117">Details</span></span>  
  
|<span data-ttu-id="457c6-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="457c6-118">Data Item Name</span></span>|<span data-ttu-id="457c6-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="457c6-119">Data Item Type</span></span>|<span data-ttu-id="457c6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="457c6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="457c6-121">Limit</span><span class="sxs-lookup"><span data-stu-id="457c6-121">Limit</span></span>|<span data-ttu-id="457c6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="457c6-122">xs:string</span></span>|<span data-ttu-id="457c6-123">È stato raggiunto il limite per la velocità MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="457c6-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="457c6-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="457c6-124">AppDomain</span></span>|<span data-ttu-id="457c6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="457c6-125">xs:string</span></span>|<span data-ttu-id="457c6-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="457c6-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
