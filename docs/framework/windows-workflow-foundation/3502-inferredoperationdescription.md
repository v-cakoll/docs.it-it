---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756091"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="75f08-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="75f08-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="75f08-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="75f08-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75f08-104">Id</span><span class="sxs-lookup"><span data-stu-id="75f08-104">ID</span></span>|<span data-ttu-id="75f08-105">3502</span><span class="sxs-lookup"><span data-stu-id="75f08-105">3502</span></span>|  
|<span data-ttu-id="75f08-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="75f08-106">Keywords</span></span>|<span data-ttu-id="75f08-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="75f08-107">WFServices</span></span>|  
|<span data-ttu-id="75f08-108">Livello</span><span class="sxs-lookup"><span data-stu-id="75f08-108">Level</span></span>|<span data-ttu-id="75f08-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="75f08-109">Information</span></span>|  
|<span data-ttu-id="75f08-110">Canale</span><span class="sxs-lookup"><span data-stu-id="75f08-110">Channel</span></span>|<span data-ttu-id="75f08-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="75f08-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="75f08-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f08-112">Description</span></span>  
 <span data-ttu-id="75f08-113">Indica che OperationDescription è stato dedotto da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="75f08-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="75f08-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="75f08-114">Message</span></span>  
 <span data-ttu-id="75f08-115">OperationDescription con Name= '%1'' nel contratto '%2' dedotta da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="75f08-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="75f08-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="75f08-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="75f08-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="75f08-117">Details</span></span>  
  
|<span data-ttu-id="75f08-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="75f08-118">Data Item Name</span></span>|<span data-ttu-id="75f08-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="75f08-119">Data Item Type</span></span>|<span data-ttu-id="75f08-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f08-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="75f08-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="75f08-121">OperationName</span></span>|<span data-ttu-id="75f08-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="75f08-122">xs:string</span></span>|<span data-ttu-id="75f08-123">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="75f08-123">The name of the operation.</span></span>|  
|<span data-ttu-id="75f08-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="75f08-124">ContractName</span></span>|<span data-ttu-id="75f08-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="75f08-125">xs:string</span></span>|<span data-ttu-id="75f08-126">Nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="75f08-126">The name of the contract.</span></span>|  
|<span data-ttu-id="75f08-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="75f08-127">IsOneWay</span></span>|<span data-ttu-id="75f08-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="75f08-128">xs:string</span></span>|<span data-ttu-id="75f08-129">True o False che indica se il contratto è unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="75f08-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="75f08-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="75f08-130">AppDomain</span></span>|<span data-ttu-id="75f08-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="75f08-131">xs:string</span></span>|<span data-ttu-id="75f08-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="75f08-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
