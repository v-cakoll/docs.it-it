---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008863"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="19e34-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="19e34-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="19e34-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="19e34-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19e34-104">Id</span><span class="sxs-lookup"><span data-stu-id="19e34-104">ID</span></span>|<span data-ttu-id="19e34-105">1018</span><span class="sxs-lookup"><span data-stu-id="19e34-105">1018</span></span>|  
|<span data-ttu-id="19e34-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="19e34-106">Keywords</span></span>|<span data-ttu-id="19e34-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="19e34-107">WFRuntime</span></span>|  
|<span data-ttu-id="19e34-108">Livello</span><span class="sxs-lookup"><span data-stu-id="19e34-108">Level</span></span>|<span data-ttu-id="19e34-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="19e34-109">Verbose</span></span>|  
|<span data-ttu-id="19e34-110">Canale</span><span class="sxs-lookup"><span data-stu-id="19e34-110">Channel</span></span>|<span data-ttu-id="19e34-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="19e34-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="19e34-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19e34-112">Description</span></span>  
 <span data-ttu-id="19e34-113">Indica che viene avviata l'esecuzione di CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="19e34-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="19e34-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="19e34-114">Message</span></span>  
 <span data-ttu-id="19e34-115">Avvio dell'esecuzione di CancelActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="19e34-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="19e34-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="19e34-116">Details</span></span>  
  
|<span data-ttu-id="19e34-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="19e34-117">Data Item Name</span></span>|<span data-ttu-id="19e34-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="19e34-118">Data Item Type</span></span>|<span data-ttu-id="19e34-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19e34-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="19e34-120">Attività</span><span class="sxs-lookup"><span data-stu-id="19e34-120">Activity</span></span>|<span data-ttu-id="19e34-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="19e34-121">xs:string</span></span>|<span data-ttu-id="19e34-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="19e34-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="19e34-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="19e34-123">DisplayName</span></span>|<span data-ttu-id="19e34-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="19e34-124">xs:string</span></span>|<span data-ttu-id="19e34-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="19e34-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="19e34-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="19e34-126">InstanceId</span></span>|<span data-ttu-id="19e34-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="19e34-127">xs:string</span></span>|<span data-ttu-id="19e34-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="19e34-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="19e34-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="19e34-129">AppDomain</span></span>|<span data-ttu-id="19e34-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="19e34-130">xs:string</span></span>|<span data-ttu-id="19e34-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="19e34-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
