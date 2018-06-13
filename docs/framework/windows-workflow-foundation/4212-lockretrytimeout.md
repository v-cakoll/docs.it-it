---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511267"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="7185e-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="7185e-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="7185e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7185e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7185e-104">ID</span><span class="sxs-lookup"><span data-stu-id="7185e-104">ID</span></span>|<span data-ttu-id="7185e-105">4212</span><span class="sxs-lookup"><span data-stu-id="7185e-105">4212</span></span>|  
|<span data-ttu-id="7185e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7185e-106">Keywords</span></span>|<span data-ttu-id="7185e-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="7185e-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="7185e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="7185e-108">Level</span></span>|<span data-ttu-id="7185e-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="7185e-109">Warning</span></span>|  
|<span data-ttu-id="7185e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="7185e-110">Channel</span></span>|<span data-ttu-id="7185e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7185e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7185e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7185e-112">Description</span></span>  
 <span data-ttu-id="7185e-113">Timeout rilevato del provider SQL durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="7185e-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7185e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="7185e-114">Message</span></span>  
 <span data-ttu-id="7185e-115">Timeout durante il tentativo di acquisire il blocco di istanza.</span><span class="sxs-lookup"><span data-stu-id="7185e-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="7185e-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="7185e-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="7185e-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="7185e-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7185e-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7185e-118">Details</span></span>  
  
|<span data-ttu-id="7185e-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="7185e-119">Data Item Name</span></span>|<span data-ttu-id="7185e-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="7185e-120">Data Item Type</span></span>|<span data-ttu-id="7185e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7185e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7185e-122">Delay</span><span class="sxs-lookup"><span data-stu-id="7185e-122">Delay</span></span>|<span data-ttu-id="7185e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7185e-123">xs:string</span></span>|<span data-ttu-id="7185e-124">Il ritardo tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="7185e-124">The delay between retries.</span></span>|  
|<span data-ttu-id="7185e-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7185e-125">AppDomain</span></span>|<span data-ttu-id="7185e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7185e-126">xs:string</span></span>|<span data-ttu-id="7185e-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7185e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
