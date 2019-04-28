---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755571"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="d0842-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="d0842-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="d0842-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d0842-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0842-104">Id</span><span class="sxs-lookup"><span data-stu-id="d0842-104">ID</span></span>|<span data-ttu-id="d0842-105">3508</span><span class="sxs-lookup"><span data-stu-id="d0842-105">3508</span></span>|  
|<span data-ttu-id="d0842-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d0842-106">Keywords</span></span>|<span data-ttu-id="d0842-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d0842-107">WFServices</span></span>|  
|<span data-ttu-id="d0842-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d0842-108">Level</span></span>|<span data-ttu-id="d0842-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="d0842-109">Verbose</span></span>|  
|<span data-ttu-id="d0842-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d0842-110">Channel</span></span>|<span data-ttu-id="d0842-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d0842-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0842-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0842-112">Description</span></span>  
 <span data-ttu-id="d0842-113">Indica che TrackingProfile non è presente nel file di configurazione o ActivityDefinitionId non corrisponde al profilo.</span><span class="sxs-lookup"><span data-stu-id="d0842-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0842-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d0842-114">Message</span></span>  
 <span data-ttu-id="d0842-115">Impossibile trovare TrackingProfile '%1' per ActivityDefinitionId '%2'.</span><span class="sxs-lookup"><span data-stu-id="d0842-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="d0842-116">TrackingProfile non incluso nel file di configurazione o ActivityDefinitionId non corrisponde.</span><span class="sxs-lookup"><span data-stu-id="d0842-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0842-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d0842-117">Details</span></span>  
  
|<span data-ttu-id="d0842-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d0842-118">Data Item Name</span></span>|<span data-ttu-id="d0842-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d0842-119">Data Item Type</span></span>|<span data-ttu-id="d0842-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0842-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0842-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="d0842-121">TrackingProfile</span></span>|<span data-ttu-id="d0842-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0842-122">xs:string</span></span>|<span data-ttu-id="d0842-123">Nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d0842-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="d0842-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="d0842-124">ActivityDefinitionId</span></span>|<span data-ttu-id="d0842-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0842-125">xs:string</span></span>|<span data-ttu-id="d0842-126">ID di definizione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d0842-126">The activity definition id.</span></span>|  
|<span data-ttu-id="d0842-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0842-127">AppDomain</span></span>|<span data-ttu-id="d0842-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0842-128">xs:string</span></span>|<span data-ttu-id="d0842-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d0842-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
