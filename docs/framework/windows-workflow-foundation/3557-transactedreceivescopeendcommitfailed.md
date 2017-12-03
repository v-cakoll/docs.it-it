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
ms.openlocfilehash: 8ea57cc60f9626763308267a98624c825f8312b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="c640d-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="c640d-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="c640d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c640d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c640d-104">ID</span><span class="sxs-lookup"><span data-stu-id="c640d-104">ID</span></span>|<span data-ttu-id="c640d-105">3557</span><span class="sxs-lookup"><span data-stu-id="c640d-105">3557</span></span>|  
|<span data-ttu-id="c640d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c640d-106">Keywords</span></span>|<span data-ttu-id="c640d-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="c640d-107">WFServices</span></span>|  
|<span data-ttu-id="c640d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c640d-108">Level</span></span>|<span data-ttu-id="c640d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="c640d-109">Information</span></span>|  
|<span data-ttu-id="c640d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c640d-110">Channel</span></span>|<span data-ttu-id="c640d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c640d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c640d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c640d-112">Description</span></span>  
 <span data-ttu-id="c640d-113">Indica che la chiamata a EndCommit in CommittableTransaction ha generato TransactionException.</span><span class="sxs-lookup"><span data-stu-id="c640d-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c640d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c640d-114">Message</span></span>  
 <span data-ttu-id="c640d-115">La chiamata a EndCommit in CommittableTransaction con ID = '%1' ha generato TransactionException con il messaggio seguente: '%2'.</span><span class="sxs-lookup"><span data-stu-id="c640d-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c640d-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c640d-116">Details</span></span>  
  
|<span data-ttu-id="c640d-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c640d-117">Data Item Name</span></span>|<span data-ttu-id="c640d-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c640d-118">Data Item Type</span></span>|<span data-ttu-id="c640d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c640d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c640d-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="c640d-120">TransactionId</span></span>|<span data-ttu-id="c640d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c640d-121">xs:string</span></span>|<span data-ttu-id="c640d-122">ID della transazione di cui eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="c640d-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="c640d-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="c640d-123">Exception</span></span>|<span data-ttu-id="c640d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c640d-124">xs:string</span></span>|<span data-ttu-id="c640d-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c640d-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="c640d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c640d-126">AppDomain</span></span>|<span data-ttu-id="c640d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c640d-127">xs:string</span></span>|<span data-ttu-id="c640d-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c640d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
