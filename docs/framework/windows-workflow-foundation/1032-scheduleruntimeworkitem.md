---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924865"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="13f05-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="13f05-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="13f05-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="13f05-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13f05-104">Id</span><span class="sxs-lookup"><span data-stu-id="13f05-104">ID</span></span>|<span data-ttu-id="13f05-105">1032</span><span class="sxs-lookup"><span data-stu-id="13f05-105">1032</span></span>|  
|<span data-ttu-id="13f05-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13f05-106">Keywords</span></span>|<span data-ttu-id="13f05-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="13f05-107">WFRuntime</span></span>|  
|<span data-ttu-id="13f05-108">Livello</span><span class="sxs-lookup"><span data-stu-id="13f05-108">Level</span></span>|<span data-ttu-id="13f05-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="13f05-109">Verbose</span></span>|  
|<span data-ttu-id="13f05-110">Canale</span><span class="sxs-lookup"><span data-stu-id="13f05-110">Channel</span></span>|<span data-ttu-id="13f05-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="13f05-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13f05-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13f05-112">Description</span></span>  
 <span data-ttu-id="13f05-113">Indica che un elemento RuntimeWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="13f05-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13f05-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="13f05-114">Message</span></span>  
 <span data-ttu-id="13f05-115">Elemento di lavoro del runtime pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="13f05-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13f05-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="13f05-116">Details</span></span>  
  
|<span data-ttu-id="13f05-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="13f05-117">Data Item Name</span></span>|<span data-ttu-id="13f05-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="13f05-118">Data Item Type</span></span>|<span data-ttu-id="13f05-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13f05-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13f05-120">Attività</span><span class="sxs-lookup"><span data-stu-id="13f05-120">Activity</span></span>|<span data-ttu-id="13f05-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="13f05-121">xs:string</span></span>|<span data-ttu-id="13f05-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="13f05-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="13f05-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="13f05-123">DisplayName</span></span>|<span data-ttu-id="13f05-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="13f05-124">xs:string</span></span>|<span data-ttu-id="13f05-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="13f05-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="13f05-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="13f05-126">InstanceId</span></span>|<span data-ttu-id="13f05-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="13f05-127">xs:string</span></span>|<span data-ttu-id="13f05-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="13f05-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="13f05-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="13f05-129">AppDomain</span></span>|<span data-ttu-id="13f05-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="13f05-130">xs:string</span></span>|<span data-ttu-id="13f05-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="13f05-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
