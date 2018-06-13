---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511231"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="f5f30-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="f5f30-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="f5f30-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f5f30-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5f30-104">ID</span><span class="sxs-lookup"><span data-stu-id="f5f30-104">ID</span></span>|<span data-ttu-id="f5f30-105">3552</span><span class="sxs-lookup"><span data-stu-id="f5f30-105">3552</span></span>|  
|<span data-ttu-id="f5f30-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f5f30-106">Keywords</span></span>|<span data-ttu-id="f5f30-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="f5f30-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="f5f30-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f5f30-108">Level</span></span>|<span data-ttu-id="f5f30-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="f5f30-109">Warning</span></span>|  
|<span data-ttu-id="f5f30-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f5f30-110">Channel</span></span>|<span data-ttu-id="f5f30-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f5f30-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f5f30-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5f30-112">Description</span></span>  
 <span data-ttu-id="f5f30-113">Indica che è stato raggiunto il limite per la velocità 'MaxPendingMessagesPerChannel'.</span><span class="sxs-lookup"><span data-stu-id="f5f30-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f5f30-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f5f30-114">Message</span></span>  
 <span data-ttu-id="f5f30-115">È stato raggiunto il limite velocità 'MaxPendingMessagesPerChannel' di '%1'.</span><span class="sxs-lookup"><span data-stu-id="f5f30-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="f5f30-116">Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="f5f30-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f5f30-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f5f30-117">Details</span></span>  
  
|<span data-ttu-id="f5f30-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f5f30-118">Data Item Name</span></span>|<span data-ttu-id="f5f30-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f5f30-119">Data Item Type</span></span>|<span data-ttu-id="f5f30-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5f30-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f5f30-121">Limit</span><span class="sxs-lookup"><span data-stu-id="f5f30-121">Limit</span></span>|<span data-ttu-id="f5f30-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5f30-122">xs:string</span></span>|<span data-ttu-id="f5f30-123">È stato raggiunto il limite per la velocità MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="f5f30-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="f5f30-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f5f30-124">AppDomain</span></span>|<span data-ttu-id="f5f30-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f5f30-125">xs:string</span></span>|<span data-ttu-id="f5f30-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f5f30-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
