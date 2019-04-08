---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101777"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="111d2-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="111d2-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="111d2-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="111d2-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="111d2-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="111d2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="111d2-105">Methods</span></span>  
 <span data-ttu-id="111d2-106">La classe DeliveryRequirementsAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="111d2-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="111d2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="111d2-107">Properties</span></span>  
 <span data-ttu-id="111d2-108">La classe DeliveryRequirementsAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="111d2-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="111d2-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="111d2-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="111d2-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="111d2-110">Data type: string</span></span>  
  
 <span data-ttu-id="111d2-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="111d2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="111d2-112">Specifica se l'associazione di un servizio supporta i contratti.</span><span class="sxs-lookup"><span data-stu-id="111d2-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="111d2-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="111d2-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="111d2-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="111d2-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="111d2-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="111d2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="111d2-116">Specifica se l'associazione supporta i messaggi ordinati.</span><span class="sxs-lookup"><span data-stu-id="111d2-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="111d2-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="111d2-117">TargetContract</span></span>  
 <span data-ttu-id="111d2-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="111d2-118">Data type: string</span></span>  
  
 <span data-ttu-id="111d2-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="111d2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="111d2-120">Contratto a cui viene applicato.</span><span class="sxs-lookup"><span data-stu-id="111d2-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="111d2-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="111d2-121">Requirements</span></span>  
  
|<span data-ttu-id="111d2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="111d2-122">MOF</span></span>|<span data-ttu-id="111d2-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="111d2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="111d2-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="111d2-124">Namespace</span></span>|<span data-ttu-id="111d2-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="111d2-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="111d2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="111d2-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
