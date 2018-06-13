---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510283"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="c1600-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="c1600-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c1600-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c1600-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1600-104">ID</span><span class="sxs-lookup"><span data-stu-id="c1600-104">ID</span></span>|<span data-ttu-id="c1600-105">1026</span><span class="sxs-lookup"><span data-stu-id="c1600-105">1026</span></span>|  
|<span data-ttu-id="c1600-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c1600-106">Keywords</span></span>|<span data-ttu-id="c1600-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c1600-107">WFRuntime</span></span>|  
|<span data-ttu-id="c1600-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c1600-108">Level</span></span>|<span data-ttu-id="c1600-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="c1600-109">Verbose</span></span>|  
|<span data-ttu-id="c1600-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c1600-110">Channel</span></span>|<span data-ttu-id="c1600-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c1600-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c1600-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1600-112">Description</span></span>  
 <span data-ttu-id="c1600-113">Indica che un elemento TransactionContextWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="c1600-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c1600-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c1600-114">Message</span></span>  
 <span data-ttu-id="c1600-115">TransactionContextWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c1600-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c1600-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c1600-116">Details</span></span>  
  
|<span data-ttu-id="c1600-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c1600-117">Data Item Name</span></span>|<span data-ttu-id="c1600-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c1600-118">Data Item Type</span></span>|<span data-ttu-id="c1600-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1600-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c1600-120">Attività</span><span class="sxs-lookup"><span data-stu-id="c1600-120">Activity</span></span>|<span data-ttu-id="c1600-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1600-121">xs:string</span></span>|<span data-ttu-id="c1600-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="c1600-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c1600-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c1600-123">DisplayName</span></span>|<span data-ttu-id="c1600-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1600-124">xs:string</span></span>|<span data-ttu-id="c1600-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c1600-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c1600-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c1600-126">InstanceId</span></span>|<span data-ttu-id="c1600-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1600-127">xs:string</span></span>|<span data-ttu-id="c1600-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="c1600-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c1600-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c1600-129">AppDomain</span></span>|<span data-ttu-id="c1600-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1600-130">xs:string</span></span>|<span data-ttu-id="c1600-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c1600-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
