---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924215"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="23642-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="23642-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="23642-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="23642-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23642-104">Id</span><span class="sxs-lookup"><span data-stu-id="23642-104">ID</span></span>|<span data-ttu-id="23642-105">1132</span><span class="sxs-lookup"><span data-stu-id="23642-105">1132</span></span>|  
|<span data-ttu-id="23642-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="23642-106">Keywords</span></span>|<span data-ttu-id="23642-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="23642-107">WFRuntime</span></span>|  
|<span data-ttu-id="23642-108">Livello</span><span class="sxs-lookup"><span data-stu-id="23642-108">Level</span></span>|<span data-ttu-id="23642-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="23642-109">Information</span></span>|  
|<span data-ttu-id="23642-110">Canale</span><span class="sxs-lookup"><span data-stu-id="23642-110">Channel</span></span>|<span data-ttu-id="23642-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="23642-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23642-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23642-112">Description</span></span>  
 <span data-ttu-id="23642-113">Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che non viene usato il modello asincrono quando viene richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="23642-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23642-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="23642-114">Message</span></span>  
 <span data-ttu-id="23642-115">InvokeMethod '%1': il metodo non usa un modello asincrono.</span><span class="sxs-lookup"><span data-stu-id="23642-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23642-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="23642-116">Details</span></span>  
  
|<span data-ttu-id="23642-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="23642-117">Data Item Name</span></span>|<span data-ttu-id="23642-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="23642-118">Data Item Type</span></span>|<span data-ttu-id="23642-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23642-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23642-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="23642-120">InvokeMethod</span></span>|<span data-ttu-id="23642-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="23642-121">xs:string</span></span>|<span data-ttu-id="23642-122">Nome visualizzato dell'attività InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="23642-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="23642-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23642-123">AppDomain</span></span>|<span data-ttu-id="23642-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="23642-124">xs:string</span></span>|<span data-ttu-id="23642-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="23642-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
