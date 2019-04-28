---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924488"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="ec33b-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ec33b-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ec33b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ec33b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec33b-104">Id</span><span class="sxs-lookup"><span data-stu-id="ec33b-104">ID</span></span>|<span data-ttu-id="ec33b-105">1017</span><span class="sxs-lookup"><span data-stu-id="ec33b-105">1017</span></span>|  
|<span data-ttu-id="ec33b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ec33b-106">Keywords</span></span>|<span data-ttu-id="ec33b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ec33b-107">WFRuntime</span></span>|  
|<span data-ttu-id="ec33b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ec33b-108">Level</span></span>|<span data-ttu-id="ec33b-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="ec33b-109">Verbose</span></span>|  
|<span data-ttu-id="ec33b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ec33b-110">Channel</span></span>|<span data-ttu-id="ec33b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ec33b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec33b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec33b-112">Description</span></span>  
 <span data-ttu-id="ec33b-113">Indica che un elemento CancelActivityWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="ec33b-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec33b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ec33b-114">Message</span></span>  
 <span data-ttu-id="ec33b-115">CancelActivityWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ec33b-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec33b-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ec33b-116">Details</span></span>  
  
|<span data-ttu-id="ec33b-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ec33b-117">Data Item Name</span></span>|<span data-ttu-id="ec33b-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ec33b-118">Data Item Type</span></span>|<span data-ttu-id="ec33b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec33b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec33b-120">Attività</span><span class="sxs-lookup"><span data-stu-id="ec33b-120">Activity</span></span>|<span data-ttu-id="ec33b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec33b-121">xs:string</span></span>|<span data-ttu-id="ec33b-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="ec33b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ec33b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ec33b-123">DisplayName</span></span>|<span data-ttu-id="ec33b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec33b-124">xs:string</span></span>|<span data-ttu-id="ec33b-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ec33b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ec33b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ec33b-126">InstanceId</span></span>|<span data-ttu-id="ec33b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec33b-127">xs:string</span></span>|<span data-ttu-id="ec33b-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ec33b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ec33b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ec33b-129">AppDomain</span></span>|<span data-ttu-id="ec33b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec33b-130">xs:string</span></span>|<span data-ttu-id="ec33b-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ec33b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
