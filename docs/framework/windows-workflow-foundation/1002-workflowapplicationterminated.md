---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008655"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="d0748-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="d0748-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="d0748-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d0748-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0748-104">Id</span><span class="sxs-lookup"><span data-stu-id="d0748-104">ID</span></span>|<span data-ttu-id="d0748-105">1002</span><span class="sxs-lookup"><span data-stu-id="d0748-105">1002</span></span>|  
|<span data-ttu-id="d0748-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d0748-106">Keywords</span></span>|<span data-ttu-id="d0748-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d0748-107">WFRuntime</span></span>|  
|<span data-ttu-id="d0748-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d0748-108">Level</span></span>|<span data-ttu-id="d0748-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="d0748-109">Information</span></span>|  
|<span data-ttu-id="d0748-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d0748-110">Channel</span></span>|<span data-ttu-id="d0748-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d0748-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0748-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0748-112">Description</span></span>  
 <span data-ttu-id="d0748-113">Indica che un'applicazione flusso di lavoro è terminata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d0748-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0748-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d0748-114">Message</span></span>  
 <span data-ttu-id="d0748-115">WorkflowApplication con ID: '%1' terminata.</span><span class="sxs-lookup"><span data-stu-id="d0748-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="d0748-116">È stata completata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d0748-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0748-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d0748-117">Details</span></span>  
  
|<span data-ttu-id="d0748-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d0748-118">Data Item Name</span></span>|<span data-ttu-id="d0748-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d0748-119">Data Item Type</span></span>|<span data-ttu-id="d0748-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0748-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0748-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="d0748-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="d0748-122">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d0748-122">The workflow application id</span></span>|  
|<span data-ttu-id="d0748-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="d0748-123">Exception</span></span>|`xs:string`|<span data-ttu-id="d0748-124">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d0748-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="d0748-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0748-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d0748-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d0748-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
