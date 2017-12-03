---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 172f7df4f028c1ddc0f5565e95291e857ee6fa1d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="ac403-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="ac403-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="ac403-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="ac403-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac403-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac403-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ac403-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ac403-105">Methods</span></span>  
 <span data-ttu-id="ac403-106">La classe DeliveryRequirementsAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="ac403-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ac403-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ac403-107">Properties</span></span>  
 <span data-ttu-id="ac403-108">La classe DeliveryRequirementsAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac403-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="ac403-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="ac403-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="ac403-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ac403-110">Data type: string</span></span>  
  
 <span data-ttu-id="ac403-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ac403-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ac403-112">Specifica se l'associazione di un servizio supporta i contratti.</span><span class="sxs-lookup"><span data-stu-id="ac403-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="ac403-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="ac403-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="ac403-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="ac403-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ac403-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ac403-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ac403-116">Specifica se l'associazione supporta i messaggi ordinati.</span><span class="sxs-lookup"><span data-stu-id="ac403-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="ac403-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="ac403-117">TargetContract</span></span>  
 <span data-ttu-id="ac403-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="ac403-118">Data type: string</span></span>  
  
 <span data-ttu-id="ac403-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="ac403-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ac403-120">Contratto a cui viene applicato.</span><span class="sxs-lookup"><span data-stu-id="ac403-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac403-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac403-121">Requirements</span></span>  
  
|<span data-ttu-id="ac403-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ac403-122">MOF</span></span>|<span data-ttu-id="ac403-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ac403-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ac403-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ac403-124">Namespace</span></span>|<span data-ttu-id="ac403-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ac403-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac403-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac403-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
