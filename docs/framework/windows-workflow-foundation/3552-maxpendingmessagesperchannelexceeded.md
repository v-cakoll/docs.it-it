---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945938"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="d0735-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="d0735-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="d0735-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d0735-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0735-104">Id</span><span class="sxs-lookup"><span data-stu-id="d0735-104">ID</span></span>|<span data-ttu-id="d0735-105">3552</span><span class="sxs-lookup"><span data-stu-id="d0735-105">3552</span></span>|  
|<span data-ttu-id="d0735-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d0735-106">Keywords</span></span>|<span data-ttu-id="d0735-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="d0735-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="d0735-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d0735-108">Level</span></span>|<span data-ttu-id="d0735-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="d0735-109">Warning</span></span>|  
|<span data-ttu-id="d0735-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d0735-110">Channel</span></span>|<span data-ttu-id="d0735-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d0735-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0735-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0735-112">Description</span></span>  
 <span data-ttu-id="d0735-113">Indica che è stato raggiunto il limite per la velocità 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="d0735-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0735-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d0735-114">Message</span></span>  
 <span data-ttu-id="d0735-115">Per la velocità 'MaxPendingMessagesPerChannel' limite di '%1' è stato raggiunto.</span><span class="sxs-lookup"><span data-stu-id="d0735-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="d0735-116">Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="d0735-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0735-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d0735-117">Details</span></span>  
  
|<span data-ttu-id="d0735-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d0735-118">Data Item Name</span></span>|<span data-ttu-id="d0735-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d0735-119">Data Item Type</span></span>|<span data-ttu-id="d0735-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0735-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0735-121">Limit</span><span class="sxs-lookup"><span data-stu-id="d0735-121">Limit</span></span>|<span data-ttu-id="d0735-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0735-122">xs:string</span></span>|<span data-ttu-id="d0735-123">È stato raggiunto il limite per la velocità MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="d0735-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="d0735-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0735-124">AppDomain</span></span>|<span data-ttu-id="d0735-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0735-125">xs:string</span></span>|<span data-ttu-id="d0735-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d0735-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
