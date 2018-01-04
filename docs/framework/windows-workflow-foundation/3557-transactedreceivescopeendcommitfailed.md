---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 85e9456f6b4c1884b2e28671b304728135b6b1d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="342c6-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="342c6-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="342c6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="342c6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="342c6-104">ID</span><span class="sxs-lookup"><span data-stu-id="342c6-104">ID</span></span>|<span data-ttu-id="342c6-105">3557</span><span class="sxs-lookup"><span data-stu-id="342c6-105">3557</span></span>|  
|<span data-ttu-id="342c6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="342c6-106">Keywords</span></span>|<span data-ttu-id="342c6-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="342c6-107">WFServices</span></span>|  
|<span data-ttu-id="342c6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="342c6-108">Level</span></span>|<span data-ttu-id="342c6-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="342c6-109">Information</span></span>|  
|<span data-ttu-id="342c6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="342c6-110">Channel</span></span>|<span data-ttu-id="342c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="342c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="342c6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342c6-112">Description</span></span>  
 <span data-ttu-id="342c6-113">Indica che la chiamata a EndCommit in CommittableTransaction ha generato TransactionException.</span><span class="sxs-lookup"><span data-stu-id="342c6-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="342c6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="342c6-114">Message</span></span>  
 <span data-ttu-id="342c6-115">La chiamata a EndCommit in CommittableTransaction con ID = '%1' ha generato TransactionException con il messaggio seguente: '%2'.</span><span class="sxs-lookup"><span data-stu-id="342c6-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="342c6-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="342c6-116">Details</span></span>  
  
|<span data-ttu-id="342c6-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="342c6-117">Data Item Name</span></span>|<span data-ttu-id="342c6-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="342c6-118">Data Item Type</span></span>|<span data-ttu-id="342c6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="342c6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="342c6-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="342c6-120">TransactionId</span></span>|<span data-ttu-id="342c6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="342c6-121">xs:string</span></span>|<span data-ttu-id="342c6-122">ID della transazione di cui eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="342c6-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="342c6-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="342c6-123">Exception</span></span>|<span data-ttu-id="342c6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="342c6-124">xs:string</span></span>|<span data-ttu-id="342c6-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="342c6-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="342c6-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="342c6-126">AppDomain</span></span>|<span data-ttu-id="342c6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="342c6-127">xs:string</span></span>|<span data-ttu-id="342c6-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="342c6-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
