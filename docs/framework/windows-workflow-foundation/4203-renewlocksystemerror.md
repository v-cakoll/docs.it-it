---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513929"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="32a03-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="32a03-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="32a03-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="32a03-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="32a03-104">ID</span><span class="sxs-lookup"><span data-stu-id="32a03-104">ID</span></span>|<span data-ttu-id="32a03-105">4203</span><span class="sxs-lookup"><span data-stu-id="32a03-105">4203</span></span>|  
|<span data-ttu-id="32a03-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="32a03-106">Keywords</span></span>|<span data-ttu-id="32a03-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="32a03-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="32a03-108">Livello</span><span class="sxs-lookup"><span data-stu-id="32a03-108">Level</span></span>|<span data-ttu-id="32a03-109">Errore</span><span class="sxs-lookup"><span data-stu-id="32a03-109">Error</span></span>|  
|<span data-ttu-id="32a03-110">Canale</span><span class="sxs-lookup"><span data-stu-id="32a03-110">Channel</span></span>|<span data-ttu-id="32a03-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="32a03-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="32a03-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32a03-112">Description</span></span>  
 <span data-ttu-id="32a03-113">Indica che il provider SQL non è in grado di estendere la scadenza del blocco perché la scadenza è già passata o il proprietario del blocco è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="32a03-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="32a03-114">SqlWorkflowInstanceStore verrà interrotto.</span><span class="sxs-lookup"><span data-stu-id="32a03-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="32a03-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="32a03-115">Message</span></span>  
 <span data-ttu-id="32a03-116">Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato.</span><span class="sxs-lookup"><span data-stu-id="32a03-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="32a03-117">Interruzione di SqlWorkflowInstanceStore in corso.</span><span class="sxs-lookup"><span data-stu-id="32a03-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="32a03-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="32a03-118">Details</span></span>  
  
|<span data-ttu-id="32a03-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="32a03-119">Data Item Name</span></span>|<span data-ttu-id="32a03-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="32a03-120">Data Item Type</span></span>|<span data-ttu-id="32a03-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32a03-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="32a03-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="32a03-122">AppDomain</span></span>|<span data-ttu-id="32a03-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="32a03-123">xs:string</span></span>|<span data-ttu-id="32a03-124">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="32a03-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
