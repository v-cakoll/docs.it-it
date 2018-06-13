---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510393"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="aa620-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="aa620-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="aa620-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="aa620-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa620-104">ID</span><span class="sxs-lookup"><span data-stu-id="aa620-104">ID</span></span>|<span data-ttu-id="aa620-105">1036</span><span class="sxs-lookup"><span data-stu-id="aa620-105">1036</span></span>|  
|<span data-ttu-id="aa620-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="aa620-106">Keywords</span></span>|<span data-ttu-id="aa620-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aa620-107">WFRuntime</span></span>|  
|<span data-ttu-id="aa620-108">Livello</span><span class="sxs-lookup"><span data-stu-id="aa620-108">Level</span></span>|<span data-ttu-id="aa620-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="aa620-109">Verbose</span></span>|  
|<span data-ttu-id="aa620-110">Canale</span><span class="sxs-lookup"><span data-stu-id="aa620-110">Channel</span></span>|<span data-ttu-id="aa620-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aa620-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa620-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa620-112">Description</span></span>  
 <span data-ttu-id="aa620-113">Indica che un'attività ha pianificato il completamento della transazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="aa620-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa620-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="aa620-114">Message</span></span>  
 <span data-ttu-id="aa620-115">L'attività '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato il completamento della transazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="aa620-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa620-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="aa620-116">Details</span></span>  
  
|<span data-ttu-id="aa620-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="aa620-117">Data Item Name</span></span>|<span data-ttu-id="aa620-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="aa620-118">Data Item Type</span></span>|<span data-ttu-id="aa620-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa620-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa620-120">Attività</span><span class="sxs-lookup"><span data-stu-id="aa620-120">Activity</span></span>|<span data-ttu-id="aa620-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa620-121">xs:string</span></span>|<span data-ttu-id="aa620-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="aa620-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="aa620-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="aa620-123">DisplayName</span></span>|<span data-ttu-id="aa620-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa620-124">xs:string</span></span>|<span data-ttu-id="aa620-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="aa620-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="aa620-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="aa620-126">InstanceId</span></span>|<span data-ttu-id="aa620-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa620-127">xs:string</span></span>|<span data-ttu-id="aa620-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="aa620-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="aa620-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa620-129">AppDomain</span></span>|<span data-ttu-id="aa620-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa620-130">xs:string</span></span>|<span data-ttu-id="aa620-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aa620-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
