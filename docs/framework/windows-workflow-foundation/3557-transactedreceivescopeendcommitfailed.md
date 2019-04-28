---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774452"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="6e7ec-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="6e7ec-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="6e7ec-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e7ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e7ec-104">Id</span><span class="sxs-lookup"><span data-stu-id="6e7ec-104">ID</span></span>|<span data-ttu-id="6e7ec-105">3557</span><span class="sxs-lookup"><span data-stu-id="6e7ec-105">3557</span></span>|  
|<span data-ttu-id="6e7ec-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6e7ec-106">Keywords</span></span>|<span data-ttu-id="6e7ec-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="6e7ec-107">WFServices</span></span>|  
|<span data-ttu-id="6e7ec-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6e7ec-108">Level</span></span>|<span data-ttu-id="6e7ec-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6e7ec-109">Information</span></span>|  
|<span data-ttu-id="6e7ec-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6e7ec-110">Channel</span></span>|<span data-ttu-id="6e7ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6e7ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6e7ec-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e7ec-112">Description</span></span>  
 <span data-ttu-id="6e7ec-113">Indica che la chiamata a EndCommit in CommittableTransaction ha generato TransactionException.</span><span class="sxs-lookup"><span data-stu-id="6e7ec-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6e7ec-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6e7ec-114">Message</span></span>  
 <span data-ttu-id="6e7ec-115">La chiamata a EndCommit in CommittableTransaction con ID = '%1' ha generato TransactionException con il messaggio seguente: '%2'.</span><span class="sxs-lookup"><span data-stu-id="6e7ec-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6e7ec-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6e7ec-116">Details</span></span>  
  
|<span data-ttu-id="6e7ec-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6e7ec-117">Data Item Name</span></span>|<span data-ttu-id="6e7ec-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6e7ec-118">Data Item Type</span></span>|<span data-ttu-id="6e7ec-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e7ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6e7ec-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="6e7ec-120">TransactionId</span></span>|<span data-ttu-id="6e7ec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e7ec-121">xs:string</span></span>|<span data-ttu-id="6e7ec-122">ID della transazione di cui eseguire il commit.</span><span class="sxs-lookup"><span data-stu-id="6e7ec-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="6e7ec-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="6e7ec-123">Exception</span></span>|<span data-ttu-id="6e7ec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e7ec-124">xs:string</span></span>|<span data-ttu-id="6e7ec-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6e7ec-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="6e7ec-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6e7ec-126">AppDomain</span></span>|<span data-ttu-id="6e7ec-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e7ec-127">xs:string</span></span>|<span data-ttu-id="6e7ec-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6e7ec-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
