---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509616"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="2cae6-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="2cae6-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2cae6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2cae6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cae6-104">ID</span><span class="sxs-lookup"><span data-stu-id="2cae6-104">ID</span></span>|<span data-ttu-id="2cae6-105">1011</span><span class="sxs-lookup"><span data-stu-id="2cae6-105">1011</span></span>|  
|<span data-ttu-id="2cae6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2cae6-106">Keywords</span></span>|<span data-ttu-id="2cae6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2cae6-107">WFRuntime</span></span>|  
|<span data-ttu-id="2cae6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2cae6-108">Level</span></span>|<span data-ttu-id="2cae6-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="2cae6-109">Verbose</span></span>|  
|<span data-ttu-id="2cae6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2cae6-110">Channel</span></span>|<span data-ttu-id="2cae6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2cae6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2cae6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cae6-112">Description</span></span>  
 <span data-ttu-id="2cae6-113">Indica che ExecuteActivityWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="2cae6-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2cae6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2cae6-114">Message</span></span>  
 <span data-ttu-id="2cae6-115">ExecuteActivityWorkItem pianificato per l'attività '%1, DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2cae6-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2cae6-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2cae6-116">Details</span></span>  
  
|<span data-ttu-id="2cae6-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2cae6-117">Data Item Name</span></span>|<span data-ttu-id="2cae6-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2cae6-118">Data Item Type</span></span>|<span data-ttu-id="2cae6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cae6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2cae6-120">Attività</span><span class="sxs-lookup"><span data-stu-id="2cae6-120">Activity</span></span>|<span data-ttu-id="2cae6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cae6-121">xs:string</span></span>|<span data-ttu-id="2cae6-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="2cae6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2cae6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2cae6-123">DisplayName</span></span>|<span data-ttu-id="2cae6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cae6-124">xs:string</span></span>|<span data-ttu-id="2cae6-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2cae6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2cae6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2cae6-126">InstanceId</span></span>|<span data-ttu-id="2cae6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cae6-127">xs:string</span></span>|<span data-ttu-id="2cae6-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2cae6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2cae6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2cae6-129">AppDomain</span></span>|<span data-ttu-id="2cae6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2cae6-130">xs:string</span></span>|<span data-ttu-id="2cae6-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2cae6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
