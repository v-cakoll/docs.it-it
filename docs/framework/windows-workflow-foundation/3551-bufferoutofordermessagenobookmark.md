---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512232"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="dcc6c-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="dcc6c-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="dcc6c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dcc6c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dcc6c-104">ID</span><span class="sxs-lookup"><span data-stu-id="dcc6c-104">ID</span></span>|<span data-ttu-id="dcc6c-105">3551</span><span class="sxs-lookup"><span data-stu-id="dcc6c-105">3551</span></span>|  
|<span data-ttu-id="dcc6c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dcc6c-106">Keywords</span></span>|<span data-ttu-id="dcc6c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="dcc6c-107">WFServices</span></span>|  
|<span data-ttu-id="dcc6c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="dcc6c-108">Level</span></span>|<span data-ttu-id="dcc6c-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="dcc6c-109">Information</span></span>|  
|<span data-ttu-id="dcc6c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="dcc6c-110">Channel</span></span>|<span data-ttu-id="dcc6c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="dcc6c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dcc6c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcc6c-112">Description</span></span>  
 <span data-ttu-id="dcc6c-113">Indica che il riavvio di un segnalibro non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="dcc6c-114">L'operazione di ricezione memorizzata nel buffer verrà tentata nuovamente quando l'istanza del servizio sarà pronta per l'elaborazione di questa operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dcc6c-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="dcc6c-115">Message</span></span>  
 <span data-ttu-id="dcc6c-116">Impossibile eseguire l'operazione '%2' nell'istanza del servizio '%1'.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="dcc6c-117">Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dcc6c-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dcc6c-118">Details</span></span>  
  
|<span data-ttu-id="dcc6c-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="dcc6c-119">Data Item Name</span></span>|<span data-ttu-id="dcc6c-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="dcc6c-120">Data Item Type</span></span>|<span data-ttu-id="dcc6c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcc6c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dcc6c-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="dcc6c-122">OperationName</span></span>|<span data-ttu-id="dcc6c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcc6c-123">xs:string</span></span>|<span data-ttu-id="dcc6c-124">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-124">The name of the operation.</span></span>|  
|<span data-ttu-id="dcc6c-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="dcc6c-125">ServiceInstanceId</span></span>|<span data-ttu-id="dcc6c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcc6c-126">xs:string</span></span>|<span data-ttu-id="dcc6c-127">ID istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="dcc6c-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dcc6c-128">AppDomain</span></span>|<span data-ttu-id="dcc6c-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcc6c-129">xs:string</span></span>|<span data-ttu-id="dcc6c-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dcc6c-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
