---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="613d4-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="613d4-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="613d4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="613d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="613d4-104">ID</span><span class="sxs-lookup"><span data-stu-id="613d4-104">ID</span></span>|<span data-ttu-id="613d4-105">3550</span><span class="sxs-lookup"><span data-stu-id="613d4-105">3550</span></span>|  
|<span data-ttu-id="613d4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="613d4-106">Keywords</span></span>|<span data-ttu-id="613d4-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="613d4-107">WFServices</span></span>|  
|<span data-ttu-id="613d4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="613d4-108">Level</span></span>|<span data-ttu-id="613d4-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="613d4-109">Information</span></span>|  
|<span data-ttu-id="613d4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="613d4-110">Channel</span></span>|<span data-ttu-id="613d4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="613d4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="613d4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="613d4-112">Description</span></span>  
 <span data-ttu-id="613d4-113">Indica che un'operazione di ricezione memorizzata nel buffer non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="613d4-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="613d4-114">L'operazione verrà tentata nuovamente quando l'istanza del servizio sarà pronta per l'elaborazione di questa operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="613d4-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="613d4-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="613d4-115">Message</span></span>  
 <span data-ttu-id="613d4-116">Impossibile eseguire l'operazione '%1'.</span><span class="sxs-lookup"><span data-stu-id="613d4-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="613d4-117">Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="613d4-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="613d4-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="613d4-118">Details</span></span>  
  
|<span data-ttu-id="613d4-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="613d4-119">Data Item Name</span></span>|<span data-ttu-id="613d4-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="613d4-120">Data Item Type</span></span>|<span data-ttu-id="613d4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="613d4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="613d4-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="613d4-122">OperationName</span></span>|<span data-ttu-id="613d4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="613d4-123">xs:string</span></span>|<span data-ttu-id="613d4-124">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="613d4-124">The name of the operation.</span></span>|  
|<span data-ttu-id="613d4-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="613d4-125">AppDomain</span></span>|<span data-ttu-id="613d4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="613d4-126">xs:string</span></span>|<span data-ttu-id="613d4-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="613d4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
