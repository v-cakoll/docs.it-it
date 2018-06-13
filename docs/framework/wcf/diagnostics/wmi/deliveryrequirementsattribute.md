---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: d294ba4f14472012b9e311ee53742633b5173f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485804"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="546f2-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="546f2-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="546f2-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="546f2-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="546f2-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="546f2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="546f2-105">Methods</span></span>  
 <span data-ttu-id="546f2-106">La classe DeliveryRequirementsAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="546f2-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="546f2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="546f2-107">Properties</span></span>  
 <span data-ttu-id="546f2-108">La classe DeliveryRequirementsAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="546f2-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="546f2-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="546f2-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="546f2-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="546f2-110">Data type: string</span></span>  
  
 <span data-ttu-id="546f2-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="546f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="546f2-112">Specifica se l'associazione di un servizio supporta i contratti.</span><span class="sxs-lookup"><span data-stu-id="546f2-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="546f2-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="546f2-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="546f2-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="546f2-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="546f2-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="546f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="546f2-116">Specifica se l'associazione supporta i messaggi ordinati.</span><span class="sxs-lookup"><span data-stu-id="546f2-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="546f2-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="546f2-117">TargetContract</span></span>  
 <span data-ttu-id="546f2-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="546f2-118">Data type: string</span></span>  
  
 <span data-ttu-id="546f2-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="546f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="546f2-120">Contratto a cui viene applicato.</span><span class="sxs-lookup"><span data-stu-id="546f2-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="546f2-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="546f2-121">Requirements</span></span>  
  
|<span data-ttu-id="546f2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="546f2-122">MOF</span></span>|<span data-ttu-id="546f2-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="546f2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="546f2-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="546f2-124">Namespace</span></span>|<span data-ttu-id="546f2-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="546f2-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="546f2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="546f2-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
