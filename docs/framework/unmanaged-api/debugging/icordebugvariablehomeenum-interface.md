---
title: Interfaccia ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e67e4685320f56a4a6a8be2e3eb2e6c8065ce59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080384"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="a0e33-102">Interfaccia ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="a0e33-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="a0e33-103">Fornisce un enumeratore per le variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="a0e33-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0e33-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a0e33-104">Methods</span></span>  
  
|<span data-ttu-id="a0e33-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a0e33-105">Method</span></span>|<span data-ttu-id="a0e33-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0e33-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0e33-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="a0e33-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="a0e33-108">Ottiene il numero specificato di [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanze che contengono informazioni sulle variabili locali e gli argomenti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="a0e33-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0e33-109">Note</span><span class="sxs-lookup"><span data-stu-id="a0e33-109">Remarks</span></span>  
 <span data-ttu-id="a0e33-110">Il `ICorDebugVariableHomeEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="a0e33-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="a0e33-111">Un' `ICorDebugVariableHomeEnum` istanza viene popolata con [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanze chiamando il [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a0e33-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="a0e33-112">Ciascuna [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza nella raccolta rappresenta un argomento in una funzione o variabile locale.</span><span class="sxs-lookup"><span data-stu-id="a0e33-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="a0e33-113">Il [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetti nella raccolta possono essere enumerati chiamando il [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a0e33-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0e33-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0e33-114">Requirements</span></span>  
 <span data-ttu-id="a0e33-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0e33-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0e33-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0e33-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0e33-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0e33-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0e33-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0e33-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e33-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0e33-119">See also</span></span>

- [<span data-ttu-id="a0e33-120">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="a0e33-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="a0e33-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a0e33-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
