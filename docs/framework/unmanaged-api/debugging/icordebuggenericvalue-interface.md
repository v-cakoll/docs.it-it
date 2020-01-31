---
title: Interfaccia ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: e60d4b128bf03ff81863e0c95815b2c204807583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794463"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="d3ec3-102">Interfaccia ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="d3ec3-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="d3ec3-103">Sottoclasse di "ICorDebugValue" che si applica a tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="d3ec3-104">Questa interfaccia fornisce i metodi Get e Set per il valore.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3ec3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d3ec3-105">Methods</span></span>  
  
|<span data-ttu-id="d3ec3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d3ec3-106">Method</span></span>|<span data-ttu-id="d3ec3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3ec3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3ec3-108">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="d3ec3-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="d3ec3-109">Copia il valore nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="d3ec3-110">Metodo SetValue</span><span class="sxs-lookup"><span data-stu-id="d3ec3-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="d3ec3-111">Copia un nuovo valore dal buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3ec3-112">Note</span><span class="sxs-lookup"><span data-stu-id="d3ec3-112">Remarks</span></span>  
 <span data-ttu-id="d3ec3-113">`ICorDebugGenericValue` è un'interfaccia secondaria perché non utilizzabile in remoto.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="d3ec3-114">Per i tipi di riferimento, il valore è il riferimento anziché il contenuto del riferimento.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="d3ec3-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3ec3-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d3ec3-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ec3-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d3ec3-117">Requirements</span></span>  
 <span data-ttu-id="d3ec3-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ec3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ec3-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3ec3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3ec3-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3ec3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3ec3-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ec3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ec3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3ec3-122">See also</span></span>

- [<span data-ttu-id="d3ec3-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d3ec3-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
