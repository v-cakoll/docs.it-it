---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510247"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="37965-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="37965-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="37965-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37965-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37965-104">ID</span><span class="sxs-lookup"><span data-stu-id="37965-104">ID</span></span>|<span data-ttu-id="37965-105">1032</span><span class="sxs-lookup"><span data-stu-id="37965-105">1032</span></span>|  
|<span data-ttu-id="37965-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="37965-106">Keywords</span></span>|<span data-ttu-id="37965-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="37965-107">WFRuntime</span></span>|  
|<span data-ttu-id="37965-108">Livello</span><span class="sxs-lookup"><span data-stu-id="37965-108">Level</span></span>|<span data-ttu-id="37965-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="37965-109">Verbose</span></span>|  
|<span data-ttu-id="37965-110">Canale</span><span class="sxs-lookup"><span data-stu-id="37965-110">Channel</span></span>|<span data-ttu-id="37965-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="37965-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37965-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37965-112">Description</span></span>  
 <span data-ttu-id="37965-113">Indica che un elemento RuntimeWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="37965-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37965-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="37965-114">Message</span></span>  
 <span data-ttu-id="37965-115">Elemento di lavoro del runtime pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="37965-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37965-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="37965-116">Details</span></span>  
  
|<span data-ttu-id="37965-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="37965-117">Data Item Name</span></span>|<span data-ttu-id="37965-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="37965-118">Data Item Type</span></span>|<span data-ttu-id="37965-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37965-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37965-120">Attività</span><span class="sxs-lookup"><span data-stu-id="37965-120">Activity</span></span>|<span data-ttu-id="37965-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="37965-121">xs:string</span></span>|<span data-ttu-id="37965-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="37965-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="37965-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="37965-123">DisplayName</span></span>|<span data-ttu-id="37965-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="37965-124">xs:string</span></span>|<span data-ttu-id="37965-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="37965-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="37965-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="37965-126">InstanceId</span></span>|<span data-ttu-id="37965-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="37965-127">xs:string</span></span>|<span data-ttu-id="37965-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="37965-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="37965-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37965-129">AppDomain</span></span>|<span data-ttu-id="37965-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="37965-130">xs:string</span></span>|<span data-ttu-id="37965-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="37965-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
