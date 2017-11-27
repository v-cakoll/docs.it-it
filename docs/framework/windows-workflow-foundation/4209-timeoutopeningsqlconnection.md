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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f87e99585ccbdf3b89653f026860e7b66dc6c9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="e36d2-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="e36d2-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="e36d2-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e36d2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e36d2-104">ID</span><span class="sxs-lookup"><span data-stu-id="e36d2-104">ID</span></span>|<span data-ttu-id="e36d2-105">4209</span><span class="sxs-lookup"><span data-stu-id="e36d2-105">4209</span></span>|  
|<span data-ttu-id="e36d2-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e36d2-106">Keywords</span></span>|<span data-ttu-id="e36d2-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e36d2-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e36d2-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e36d2-108">Level</span></span>|<span data-ttu-id="e36d2-109">Errore</span><span class="sxs-lookup"><span data-stu-id="e36d2-109">Error</span></span>|  
|<span data-ttu-id="e36d2-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e36d2-110">Channel</span></span>|<span data-ttu-id="e36d2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e36d2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e36d2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e36d2-112">Description</span></span>  
 <span data-ttu-id="e36d2-113">Indica che è stato rilevato un timeout durante il tentativo di stabilire una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="e36d2-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e36d2-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e36d2-114">Message</span></span>  
 <span data-ttu-id="e36d2-115">Timeout durante il tentativo di aprire una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="e36d2-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="e36d2-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="e36d2-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="e36d2-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="e36d2-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e36d2-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e36d2-118">Details</span></span>  
  
|<span data-ttu-id="e36d2-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e36d2-119">Data Item Name</span></span>|<span data-ttu-id="e36d2-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e36d2-120">Data Item Type</span></span>|<span data-ttu-id="e36d2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e36d2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e36d2-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="e36d2-122">Timeout</span></span>|<span data-ttu-id="e36d2-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e36d2-123">xs:string</span></span>|<span data-ttu-id="e36d2-124">Valore di timeout per l'apertura della connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="e36d2-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="e36d2-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e36d2-125">AppDomain</span></span>|<span data-ttu-id="e36d2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e36d2-126">xs:string</span></span>|<span data-ttu-id="e36d2-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e36d2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
