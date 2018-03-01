---
title: Interfaccia IEnumReferenceIdentity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d1af31c72770947c33f358a9689bac6fd95ef53c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="4fd52-102">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="4fd52-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="4fd52-103">Funge da un enumeratore per una raccolta di `IReferenceIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="4fd52-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fd52-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4fd52-104">Methods</span></span>  
  
|<span data-ttu-id="4fd52-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4fd52-105">Method</span></span>|<span data-ttu-id="4fd52-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fd52-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="4fd52-107">Ottiene un puntatore a interfaccia a un nuovo `IEnumReferenceIdentity` che contiene gli stessi membri di questo `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="4fd52-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="4fd52-108">Ottiene il numero specificato di `IReferenceIdentity` oggetti, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="4fd52-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="4fd52-109">Sposta il puntatore all'istruzione all'inizio di questo `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="4fd52-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="4fd52-110">Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="4fd52-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fd52-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4fd52-111">Requirements</span></span>  
 <span data-ttu-id="4fd52-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fd52-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fd52-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="4fd52-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4fd52-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fd52-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd52-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fd52-115">See Also</span></span>  
 [<span data-ttu-id="4fd52-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="4fd52-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="4fd52-117">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="4fd52-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
