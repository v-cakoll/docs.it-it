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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1f9f1066f1948411d584a2dee1af2129aa3a103
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="101b5-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="101b5-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="101b5-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="101b5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="101b5-104">ID</span><span class="sxs-lookup"><span data-stu-id="101b5-104">ID</span></span>|<span data-ttu-id="101b5-105">3557</span><span class="sxs-lookup"><span data-stu-id="101b5-105">3557</span></span>|  
|<span data-ttu-id="101b5-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="101b5-106">Keywords</span></span>|<span data-ttu-id="101b5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="101b5-107">WFServices</span></span>|  
|<span data-ttu-id="101b5-108">Livello</span><span class="sxs-lookup"><span data-stu-id="101b5-108">Level</span></span>|<span data-ttu-id="101b5-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="101b5-109">Information</span></span>|  
|<span data-ttu-id="101b5-110">Canale</span><span class="sxs-lookup"><span data-stu-id="101b5-110">Channel</span></span>|<span data-ttu-id="101b5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="101b5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="101b5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="101b5-112">Description</span></span>  
 <span data-ttu-id="101b5-113">Indica che la chiamata a EndCommit in CommittableTransaction ha generato TransactionException.</span><span class="sxs-lookup"><span data-stu-id="101b5-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="101b5-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="101b5-114">Message</span></span>  
 <span data-ttu-id="101b5-115">La chiamata a EndCommit in CommittableTransaction con ID = '%1' ha generato TransactionException con il messaggio seguente: '%2'.</span><span class="sxs-lookup"><span data-stu-id="101b5-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="101b5-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="101b5-116">Details</span></span>  
  
|<span data-ttu-id="101b5-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="101b5-117">Data Item Name</span></span>|<span data-ttu-id="101b5-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="101b5-118">Data Item Type</span></span>|<span data-ttu-id="101b5-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="101b5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="101b5-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="101b5-120">TransactionId</span></span>|<span data-ttu-id="101b5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="101b5-121">xs:string</span></span>|<span data-ttu-id="101b5-122">ID della transazione di cui eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="101b5-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="101b5-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="101b5-123">Exception</span></span>|<span data-ttu-id="101b5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="101b5-124">xs:string</span></span>|<span data-ttu-id="101b5-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="101b5-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="101b5-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="101b5-126">AppDomain</span></span>|<span data-ttu-id="101b5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="101b5-127">xs:string</span></span>|<span data-ttu-id="101b5-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="101b5-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
