---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7528c967cbd88f00af448d6163c10e807f603bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="3f234-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="3f234-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="3f234-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3f234-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f234-104">ID</span><span class="sxs-lookup"><span data-stu-id="3f234-104">ID</span></span>|<span data-ttu-id="3f234-105">4209</span><span class="sxs-lookup"><span data-stu-id="3f234-105">4209</span></span>|  
|<span data-ttu-id="3f234-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3f234-106">Keywords</span></span>|<span data-ttu-id="3f234-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3f234-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3f234-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3f234-108">Level</span></span>|<span data-ttu-id="3f234-109">Errore</span><span class="sxs-lookup"><span data-stu-id="3f234-109">Error</span></span>|  
|<span data-ttu-id="3f234-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3f234-110">Channel</span></span>|<span data-ttu-id="3f234-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3f234-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3f234-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f234-112">Description</span></span>  
 <span data-ttu-id="3f234-113">Indica che è stato rilevato un timeout durante il tentativo di stabilire una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="3f234-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3f234-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3f234-114">Message</span></span>  
 <span data-ttu-id="3f234-115">Timeout durante il tentativo di aprire una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="3f234-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="3f234-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="3f234-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="3f234-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="3f234-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3f234-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3f234-118">Details</span></span>  
  
|<span data-ttu-id="3f234-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3f234-119">Data Item Name</span></span>|<span data-ttu-id="3f234-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3f234-120">Data Item Type</span></span>|<span data-ttu-id="3f234-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f234-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3f234-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="3f234-122">Timeout</span></span>|<span data-ttu-id="3f234-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f234-123">xs:string</span></span>|<span data-ttu-id="3f234-124">Valore di timeout per l'apertura della connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="3f234-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="3f234-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3f234-125">AppDomain</span></span>|<span data-ttu-id="3f234-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f234-126">xs:string</span></span>|<span data-ttu-id="3f234-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3f234-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
