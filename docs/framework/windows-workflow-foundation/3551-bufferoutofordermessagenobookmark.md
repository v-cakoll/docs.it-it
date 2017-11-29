---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a380def22c270a3fafe118a426609a93862c447
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="2543f-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="2543f-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="2543f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2543f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2543f-104">ID</span><span class="sxs-lookup"><span data-stu-id="2543f-104">ID</span></span>|<span data-ttu-id="2543f-105">3551</span><span class="sxs-lookup"><span data-stu-id="2543f-105">3551</span></span>|  
|<span data-ttu-id="2543f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2543f-106">Keywords</span></span>|<span data-ttu-id="2543f-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="2543f-107">WFServices</span></span>|  
|<span data-ttu-id="2543f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2543f-108">Level</span></span>|<span data-ttu-id="2543f-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2543f-109">Information</span></span>|  
|<span data-ttu-id="2543f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2543f-110">Channel</span></span>|<span data-ttu-id="2543f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2543f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2543f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2543f-112">Description</span></span>  
 <span data-ttu-id="2543f-113">Indica che il riavvio di un segnalibro non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="2543f-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="2543f-114">L'operazione di ricezione memorizzata nel buffer verrà tentata nuovamente quando l'istanza del servizio sarà pronta per l'elaborazione di questa operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="2543f-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2543f-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2543f-115">Message</span></span>  
 <span data-ttu-id="2543f-116">Impossibile eseguire l'operazione '%2' nell'istanza del servizio '%1'.</span><span class="sxs-lookup"><span data-stu-id="2543f-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="2543f-117">Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="2543f-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2543f-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2543f-118">Details</span></span>  
  
|<span data-ttu-id="2543f-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2543f-119">Data Item Name</span></span>|<span data-ttu-id="2543f-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2543f-120">Data Item Type</span></span>|<span data-ttu-id="2543f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2543f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2543f-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="2543f-122">OperationName</span></span>|<span data-ttu-id="2543f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="2543f-123">xs:string</span></span>|<span data-ttu-id="2543f-124">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="2543f-124">The name of the operation.</span></span>|  
|<span data-ttu-id="2543f-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="2543f-125">ServiceInstanceId</span></span>|<span data-ttu-id="2543f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="2543f-126">xs:string</span></span>|<span data-ttu-id="2543f-127">ID istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="2543f-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="2543f-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2543f-128">AppDomain</span></span>|<span data-ttu-id="2543f-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="2543f-129">xs:string</span></span>|<span data-ttu-id="2543f-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2543f-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
