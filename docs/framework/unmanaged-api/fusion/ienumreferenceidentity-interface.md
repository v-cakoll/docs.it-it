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
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796436"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="c7077-102">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="c7077-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="c7077-103">Funge da enumeratore per una raccolta di `IReferenceIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="c7077-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7077-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c7077-104">Methods</span></span>  
  
|<span data-ttu-id="c7077-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c7077-105">Method</span></span>|<span data-ttu-id="c7077-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7077-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="c7077-107">Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` nuovo oggetto che contiene gli stessi membri `IEnumReferenceIdentity`di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="c7077-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="c7077-108">Ottiene il numero specificato di `IReferenceIdentity` oggetti, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c7077-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="c7077-109">Sposta il puntatore all'istruzione all'inizio di questo `IEnumReferenceIdentity`oggetto.</span><span class="sxs-lookup"><span data-stu-id="c7077-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="c7077-110">Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c7077-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7077-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7077-111">Requirements</span></span>  
 <span data-ttu-id="c7077-112">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7077-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7077-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="c7077-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c7077-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7077-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7077-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7077-115">See also</span></span>

- [<span data-ttu-id="c7077-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="c7077-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="c7077-117">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="c7077-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
