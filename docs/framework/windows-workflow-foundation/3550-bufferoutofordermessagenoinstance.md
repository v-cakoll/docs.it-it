---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755584"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="5d915-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="5d915-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="5d915-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5d915-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d915-104">Id</span><span class="sxs-lookup"><span data-stu-id="5d915-104">ID</span></span>|<span data-ttu-id="5d915-105">3550</span><span class="sxs-lookup"><span data-stu-id="5d915-105">3550</span></span>|  
|<span data-ttu-id="5d915-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5d915-106">Keywords</span></span>|<span data-ttu-id="5d915-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="5d915-107">WFServices</span></span>|  
|<span data-ttu-id="5d915-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5d915-108">Level</span></span>|<span data-ttu-id="5d915-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="5d915-109">Information</span></span>|  
|<span data-ttu-id="5d915-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5d915-110">Channel</span></span>|<span data-ttu-id="5d915-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5d915-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d915-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d915-112">Description</span></span>  
 <span data-ttu-id="5d915-113">Indica che un'operazione di ricezione memorizzata nel buffer non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5d915-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="5d915-114">L'operazione verrà tentata nuovamente quando l'istanza del servizio sarà pronta per l'elaborazione di questa operazione specifica.</span><span class="sxs-lookup"><span data-stu-id="5d915-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d915-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5d915-115">Message</span></span>  
 <span data-ttu-id="5d915-116">Impossibile eseguire l'operazione '%1'.</span><span class="sxs-lookup"><span data-stu-id="5d915-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="5d915-117">Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="5d915-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d915-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5d915-118">Details</span></span>  
  
|<span data-ttu-id="5d915-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5d915-119">Data Item Name</span></span>|<span data-ttu-id="5d915-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5d915-120">Data Item Type</span></span>|<span data-ttu-id="5d915-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d915-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d915-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="5d915-122">OperationName</span></span>|<span data-ttu-id="5d915-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d915-123">xs:string</span></span>|<span data-ttu-id="5d915-124">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5d915-124">The name of the operation.</span></span>|  
|<span data-ttu-id="5d915-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d915-125">AppDomain</span></span>|<span data-ttu-id="5d915-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d915-126">xs:string</span></span>|<span data-ttu-id="5d915-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d915-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
