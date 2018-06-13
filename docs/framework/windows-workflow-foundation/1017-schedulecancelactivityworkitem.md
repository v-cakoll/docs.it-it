---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510172"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="3b71e-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3b71e-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3b71e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3b71e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b71e-104">ID</span><span class="sxs-lookup"><span data-stu-id="3b71e-104">ID</span></span>|<span data-ttu-id="3b71e-105">1017</span><span class="sxs-lookup"><span data-stu-id="3b71e-105">1017</span></span>|  
|<span data-ttu-id="3b71e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3b71e-106">Keywords</span></span>|<span data-ttu-id="3b71e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3b71e-107">WFRuntime</span></span>|  
|<span data-ttu-id="3b71e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3b71e-108">Level</span></span>|<span data-ttu-id="3b71e-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="3b71e-109">Verbose</span></span>|  
|<span data-ttu-id="3b71e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3b71e-110">Channel</span></span>|<span data-ttu-id="3b71e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3b71e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b71e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b71e-112">Description</span></span>  
 <span data-ttu-id="3b71e-113">Indica che un elemento CancelActivityWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="3b71e-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b71e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3b71e-114">Message</span></span>  
 <span data-ttu-id="3b71e-115">CancelActivityWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3b71e-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b71e-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3b71e-116">Details</span></span>  
  
|<span data-ttu-id="3b71e-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3b71e-117">Data Item Name</span></span>|<span data-ttu-id="3b71e-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3b71e-118">Data Item Type</span></span>|<span data-ttu-id="3b71e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b71e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b71e-120">Attività</span><span class="sxs-lookup"><span data-stu-id="3b71e-120">Activity</span></span>|<span data-ttu-id="3b71e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b71e-121">xs:string</span></span>|<span data-ttu-id="3b71e-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="3b71e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3b71e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3b71e-123">DisplayName</span></span>|<span data-ttu-id="3b71e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b71e-124">xs:string</span></span>|<span data-ttu-id="3b71e-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3b71e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3b71e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3b71e-126">InstanceId</span></span>|<span data-ttu-id="3b71e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b71e-127">xs:string</span></span>|<span data-ttu-id="3b71e-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="3b71e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3b71e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b71e-129">AppDomain</span></span>|<span data-ttu-id="3b71e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b71e-130">xs:string</span></span>|<span data-ttu-id="3b71e-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3b71e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
