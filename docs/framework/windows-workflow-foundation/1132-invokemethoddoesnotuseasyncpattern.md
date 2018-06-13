---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511875"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="c97a8-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="c97a8-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="c97a8-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c97a8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c97a8-104">ID</span><span class="sxs-lookup"><span data-stu-id="c97a8-104">ID</span></span>|<span data-ttu-id="c97a8-105">1132</span><span class="sxs-lookup"><span data-stu-id="c97a8-105">1132</span></span>|  
|<span data-ttu-id="c97a8-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c97a8-106">Keywords</span></span>|<span data-ttu-id="c97a8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c97a8-107">WFRuntime</span></span>|  
|<span data-ttu-id="c97a8-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c97a8-108">Level</span></span>|<span data-ttu-id="c97a8-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="c97a8-109">Information</span></span>|  
|<span data-ttu-id="c97a8-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c97a8-110">Channel</span></span>|<span data-ttu-id="c97a8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c97a8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c97a8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c97a8-112">Description</span></span>  
 <span data-ttu-id="c97a8-113">Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che non viene usato il modello asincrono quando viene richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="c97a8-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c97a8-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c97a8-114">Message</span></span>  
 <span data-ttu-id="c97a8-115">InvokeMethod '%1': il metodo non usa un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="c97a8-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c97a8-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c97a8-116">Details</span></span>  
  
|<span data-ttu-id="c97a8-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c97a8-117">Data Item Name</span></span>|<span data-ttu-id="c97a8-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c97a8-118">Data Item Type</span></span>|<span data-ttu-id="c97a8-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c97a8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c97a8-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="c97a8-120">InvokeMethod</span></span>|<span data-ttu-id="c97a8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c97a8-121">xs:string</span></span>|<span data-ttu-id="c97a8-122">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="c97a8-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="c97a8-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c97a8-123">AppDomain</span></span>|<span data-ttu-id="c97a8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c97a8-124">xs:string</span></span>|<span data-ttu-id="c97a8-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c97a8-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
