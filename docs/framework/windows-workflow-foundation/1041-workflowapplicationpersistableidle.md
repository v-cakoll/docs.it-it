---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509667"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="cb122-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="cb122-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="cb122-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cb122-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb122-104">ID</span><span class="sxs-lookup"><span data-stu-id="cb122-104">ID</span></span>|<span data-ttu-id="cb122-105">1041</span><span class="sxs-lookup"><span data-stu-id="cb122-105">1041</span></span>|  
|<span data-ttu-id="cb122-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cb122-106">Keywords</span></span>|<span data-ttu-id="cb122-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cb122-107">WFRuntime</span></span>|  
|<span data-ttu-id="cb122-108">Livello</span><span class="sxs-lookup"><span data-stu-id="cb122-108">Level</span></span>|<span data-ttu-id="cb122-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="cb122-109">Information</span></span>|  
|<span data-ttu-id="cb122-110">Canale</span><span class="sxs-lookup"><span data-stu-id="cb122-110">Channel</span></span>|<span data-ttu-id="cb122-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cb122-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb122-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb122-112">Description</span></span>  
 <span data-ttu-id="cb122-113">Indica che un'applicazione flusso di lavoro è inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="cb122-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="cb122-114">L'applicazione flusso di lavoro verrà resa inattiva o persistente.</span><span class="sxs-lookup"><span data-stu-id="cb122-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb122-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="cb122-115">Message</span></span>  
 <span data-ttu-id="cb122-116">Workflowapplication con Id: '%1' è inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="cb122-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="cb122-117">Verrà effettuata l'azione seguente: %2.</span><span class="sxs-lookup"><span data-stu-id="cb122-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb122-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cb122-118">Details</span></span>  
  
|<span data-ttu-id="cb122-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="cb122-119">Data Item Name</span></span>|<span data-ttu-id="cb122-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="cb122-120">Data Item Type</span></span>|<span data-ttu-id="cb122-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb122-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb122-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="cb122-122">WorkflowApplicationId</span></span>|<span data-ttu-id="cb122-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb122-123">xs:string</span></span>|<span data-ttu-id="cb122-124">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cb122-124">The workflow application id</span></span>|  
|<span data-ttu-id="cb122-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="cb122-125">ActionTaken</span></span>|<span data-ttu-id="cb122-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb122-126">xs:string</span></span>|<span data-ttu-id="cb122-127">L'azione che verrà intrapresa sull'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cb122-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="cb122-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb122-128">AppDomain</span></span>|<span data-ttu-id="cb122-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb122-129">xs:string</span></span>|<span data-ttu-id="cb122-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cb122-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
