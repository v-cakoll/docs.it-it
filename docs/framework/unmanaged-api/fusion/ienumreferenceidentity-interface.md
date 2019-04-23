---
title: Interfaccia IEnumReferenceIdentity
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123487"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="34b10-102">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="34b10-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="34b10-103">Funge da un enumeratore per una raccolta di `IReferenceIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="34b10-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34b10-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="34b10-104">Methods</span></span>  
  
|<span data-ttu-id="34b10-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="34b10-105">Method</span></span>|<span data-ttu-id="34b10-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34b10-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="34b10-107">Ottiene un puntatore a interfaccia a una nuova `IEnumReferenceIdentity` che contiene gli stessi membri di questo `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="34b10-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="34b10-108">Ottiene il numero specificato di `IReferenceIdentity` oggetti, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="34b10-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="34b10-109">Sposta il puntatore all'istruzione all'inizio di questo `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="34b10-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="34b10-110">Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="34b10-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34b10-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34b10-111">Requirements</span></span>  
 <span data-ttu-id="34b10-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34b10-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b10-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="34b10-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="34b10-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b10-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34b10-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34b10-115">See also</span></span>

- [<span data-ttu-id="34b10-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="34b10-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="34b10-117">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="34b10-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
