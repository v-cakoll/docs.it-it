---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510653"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="5b254-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="5b254-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5b254-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5b254-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b254-104">ID</span><span class="sxs-lookup"><span data-stu-id="5b254-104">ID</span></span>|<span data-ttu-id="5b254-105">1018</span><span class="sxs-lookup"><span data-stu-id="5b254-105">1018</span></span>|  
|<span data-ttu-id="5b254-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5b254-106">Keywords</span></span>|<span data-ttu-id="5b254-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5b254-107">WFRuntime</span></span>|  
|<span data-ttu-id="5b254-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5b254-108">Level</span></span>|<span data-ttu-id="5b254-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="5b254-109">Verbose</span></span>|  
|<span data-ttu-id="5b254-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5b254-110">Channel</span></span>|<span data-ttu-id="5b254-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5b254-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b254-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b254-112">Description</span></span>  
 <span data-ttu-id="5b254-113">Indica che viene avviata l'esecuzione di CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="5b254-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b254-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5b254-114">Message</span></span>  
 <span data-ttu-id="5b254-115">Avvio dell'esecuzione di CancelActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="5b254-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b254-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5b254-116">Details</span></span>  
  
|<span data-ttu-id="5b254-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5b254-117">Data Item Name</span></span>|<span data-ttu-id="5b254-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5b254-118">Data Item Type</span></span>|<span data-ttu-id="5b254-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b254-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b254-120">Attività</span><span class="sxs-lookup"><span data-stu-id="5b254-120">Activity</span></span>|<span data-ttu-id="5b254-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b254-121">xs:string</span></span>|<span data-ttu-id="5b254-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="5b254-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5b254-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5b254-123">DisplayName</span></span>|<span data-ttu-id="5b254-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b254-124">xs:string</span></span>|<span data-ttu-id="5b254-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="5b254-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5b254-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5b254-126">InstanceId</span></span>|<span data-ttu-id="5b254-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b254-127">xs:string</span></span>|<span data-ttu-id="5b254-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="5b254-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5b254-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5b254-129">AppDomain</span></span>|<span data-ttu-id="5b254-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b254-130">xs:string</span></span>|<span data-ttu-id="5b254-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5b254-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
