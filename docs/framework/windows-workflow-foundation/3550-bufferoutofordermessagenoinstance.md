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
ms.workload: dotnet
ms.openlocfilehash: 435a6a4390d52555d353a25ac119934087cf9c87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="a9f1d-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="a9f1d-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="a9f1d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a9f1d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9f1d-104">ID</span><span class="sxs-lookup"><span data-stu-id="a9f1d-104">ID</span></span>|<span data-ttu-id="a9f1d-105">3550</span><span class="sxs-lookup"><span data-stu-id="a9f1d-105">3550</span></span>|  
|<span data-ttu-id="a9f1d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f1d-106">Keywords</span></span>|<span data-ttu-id="a9f1d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="a9f1d-107">WFServices</span></span>|  
|<span data-ttu-id="a9f1d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a9f1d-108">Level</span></span>|<span data-ttu-id="a9f1d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="a9f1d-109">Information</span></span>|  
|<span data-ttu-id="a9f1d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a9f1d-110">Channel</span></span>|<span data-ttu-id="a9f1d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a9f1d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a9f1d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9f1d-112">Description</span></span>  
 <span data-ttu-id="a9f1d-113">Indica che un'operazione di ricezione memorizzata nel buffer non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a9f1d-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="a9f1d-114">L'operazione verrà tentata nuovamente quando l'istanza del servizio sarà pronta per l'elaborazione di questa operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="a9f1d-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a9f1d-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a9f1d-115">Message</span></span>  
 <span data-ttu-id="a9f1d-116">Impossibile eseguire l'operazione '%1'.</span><span class="sxs-lookup"><span data-stu-id="a9f1d-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="a9f1d-117">Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="a9f1d-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a9f1d-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a9f1d-118">Details</span></span>  
  
|<span data-ttu-id="a9f1d-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a9f1d-119">Data Item Name</span></span>|<span data-ttu-id="a9f1d-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a9f1d-120">Data Item Type</span></span>|<span data-ttu-id="a9f1d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9f1d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a9f1d-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="a9f1d-122">OperationName</span></span>|<span data-ttu-id="a9f1d-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9f1d-123">xs:string</span></span>|<span data-ttu-id="a9f1d-124">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="a9f1d-124">The name of the operation.</span></span>|  
|<span data-ttu-id="a9f1d-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a9f1d-125">AppDomain</span></span>|<span data-ttu-id="a9f1d-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9f1d-126">xs:string</span></span>|<span data-ttu-id="a9f1d-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a9f1d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
