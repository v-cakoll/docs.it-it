---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510809"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="a6d75-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="a6d75-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a6d75-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a6d75-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6d75-104">ID</span><span class="sxs-lookup"><span data-stu-id="a6d75-104">ID</span></span>|<span data-ttu-id="a6d75-105">1027</span><span class="sxs-lookup"><span data-stu-id="a6d75-105">1027</span></span>|  
|<span data-ttu-id="a6d75-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a6d75-106">Keywords</span></span>|<span data-ttu-id="a6d75-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a6d75-107">WFRuntime</span></span>|  
|<span data-ttu-id="a6d75-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a6d75-108">Level</span></span>|<span data-ttu-id="a6d75-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="a6d75-109">Verbose</span></span>|  
|<span data-ttu-id="a6d75-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a6d75-110">Channel</span></span>|<span data-ttu-id="a6d75-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a6d75-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6d75-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6d75-112">Description</span></span>  
 <span data-ttu-id="a6d75-113">Indica che viene avviata l'esecuzione di TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="a6d75-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6d75-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a6d75-114">Message</span></span>  
 <span data-ttu-id="a6d75-115">Avvio dell'esecuzione di TransactionContextWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a6d75-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6d75-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a6d75-116">Details</span></span>  
  
|<span data-ttu-id="a6d75-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a6d75-117">Data Item Name</span></span>|<span data-ttu-id="a6d75-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a6d75-118">Data Item Type</span></span>|<span data-ttu-id="a6d75-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6d75-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6d75-120">Attività</span><span class="sxs-lookup"><span data-stu-id="a6d75-120">Activity</span></span>|<span data-ttu-id="a6d75-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6d75-121">xs:string</span></span>|<span data-ttu-id="a6d75-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="a6d75-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a6d75-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a6d75-123">DisplayName</span></span>|<span data-ttu-id="a6d75-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6d75-124">xs:string</span></span>|<span data-ttu-id="a6d75-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a6d75-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a6d75-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a6d75-126">InstanceId</span></span>|<span data-ttu-id="a6d75-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6d75-127">xs:string</span></span>|<span data-ttu-id="a6d75-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a6d75-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a6d75-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a6d75-129">AppDomain</span></span>|<span data-ttu-id="a6d75-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6d75-130">xs:string</span></span>|<span data-ttu-id="a6d75-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a6d75-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
