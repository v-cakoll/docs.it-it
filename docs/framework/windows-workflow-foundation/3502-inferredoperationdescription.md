---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512005"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="6849e-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="6849e-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="6849e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6849e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6849e-104">ID</span><span class="sxs-lookup"><span data-stu-id="6849e-104">ID</span></span>|<span data-ttu-id="6849e-105">3502</span><span class="sxs-lookup"><span data-stu-id="6849e-105">3502</span></span>|  
|<span data-ttu-id="6849e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6849e-106">Keywords</span></span>|<span data-ttu-id="6849e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="6849e-107">WFServices</span></span>|  
|<span data-ttu-id="6849e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6849e-108">Level</span></span>|<span data-ttu-id="6849e-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6849e-109">Information</span></span>|  
|<span data-ttu-id="6849e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6849e-110">Channel</span></span>|<span data-ttu-id="6849e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6849e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6849e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6849e-112">Description</span></span>  
 <span data-ttu-id="6849e-113">Indica che OperationDescription è stato dedotto da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="6849e-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6849e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6849e-114">Message</span></span>  
 <span data-ttu-id="6849e-115">OperationDescription con Name= '%1'' nel contratto '%2' dedotta da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="6849e-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="6849e-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="6849e-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6849e-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6849e-117">Details</span></span>  
  
|<span data-ttu-id="6849e-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6849e-118">Data Item Name</span></span>|<span data-ttu-id="6849e-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6849e-119">Data Item Type</span></span>|<span data-ttu-id="6849e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6849e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6849e-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="6849e-121">OperationName</span></span>|<span data-ttu-id="6849e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6849e-122">xs:string</span></span>|<span data-ttu-id="6849e-123">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="6849e-123">The name of the operation.</span></span>|  
|<span data-ttu-id="6849e-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="6849e-124">ContractName</span></span>|<span data-ttu-id="6849e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6849e-125">xs:string</span></span>|<span data-ttu-id="6849e-126">Nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="6849e-126">The name of the contract.</span></span>|  
|<span data-ttu-id="6849e-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="6849e-127">IsOneWay</span></span>|<span data-ttu-id="6849e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6849e-128">xs:string</span></span>|<span data-ttu-id="6849e-129">True o False che indica se il contratto è unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="6849e-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="6849e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6849e-130">AppDomain</span></span>|<span data-ttu-id="6849e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6849e-131">xs:string</span></span>|<span data-ttu-id="6849e-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6849e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
