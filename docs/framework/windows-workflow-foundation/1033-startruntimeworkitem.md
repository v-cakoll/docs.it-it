---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510066"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="21e87-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="21e87-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="21e87-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="21e87-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21e87-104">ID</span><span class="sxs-lookup"><span data-stu-id="21e87-104">ID</span></span>|<span data-ttu-id="21e87-105">1040</span><span class="sxs-lookup"><span data-stu-id="21e87-105">1033</span></span>|  
|<span data-ttu-id="21e87-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="21e87-106">Keywords</span></span>|<span data-ttu-id="21e87-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="21e87-107">WFRuntime</span></span>|  
|<span data-ttu-id="21e87-108">Livello</span><span class="sxs-lookup"><span data-stu-id="21e87-108">Level</span></span>|<span data-ttu-id="21e87-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="21e87-109">Verbose</span></span>|  
|<span data-ttu-id="21e87-110">Canale</span><span class="sxs-lookup"><span data-stu-id="21e87-110">Channel</span></span>|<span data-ttu-id="21e87-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="21e87-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="21e87-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21e87-112">Description</span></span>  
 <span data-ttu-id="21e87-113">Indica che viene avviata l'esecuzione di RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="21e87-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="21e87-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="21e87-114">Message</span></span>  
 <span data-ttu-id="21e87-115">Avvio dell'esecuzione di un elemento di lavoro del runtime per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="21e87-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="21e87-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="21e87-116">Details</span></span>  
  
|<span data-ttu-id="21e87-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="21e87-117">Data Item Name</span></span>|<span data-ttu-id="21e87-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="21e87-118">Data Item Type</span></span>|<span data-ttu-id="21e87-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21e87-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="21e87-120">Attività</span><span class="sxs-lookup"><span data-stu-id="21e87-120">Activity</span></span>|<span data-ttu-id="21e87-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="21e87-121">xs:string</span></span>|<span data-ttu-id="21e87-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="21e87-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="21e87-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="21e87-123">DisplayName</span></span>|<span data-ttu-id="21e87-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="21e87-124">xs:string</span></span>|<span data-ttu-id="21e87-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="21e87-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="21e87-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="21e87-126">InstanceId</span></span>|<span data-ttu-id="21e87-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="21e87-127">xs:string</span></span>|<span data-ttu-id="21e87-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="21e87-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="21e87-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="21e87-129">AppDomain</span></span>|<span data-ttu-id="21e87-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="21e87-130">xs:string</span></span>|<span data-ttu-id="21e87-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="21e87-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
