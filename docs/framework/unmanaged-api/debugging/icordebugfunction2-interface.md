---
title: Interfaccia ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a4349ad4dbaeafa63689ef85a307211428f8538
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917081"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="7732d-102">Interfaccia ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="7732d-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="7732d-103">Estende logicamente l'interfaccia ICorDebugFunction per fornire supporto per Just My Code il debug step-through, che ignora il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="7732d-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7732d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7732d-104">Methods</span></span>  
  
|<span data-ttu-id="7732d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7732d-105">Method</span></span>|<span data-ttu-id="7732d-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7732d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7732d-107">Metodo EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="7732d-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="7732d-108">(Non ancora implementato). Ottiene un puntatore a interfaccia a un ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="7732d-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="7732d-109">Metodo GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="7732d-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="7732d-110">Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="7732d-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="7732d-111">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="7732d-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="7732d-112">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="7732d-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="7732d-113">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="7732d-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="7732d-114">Contrassegna questa funzione per Just My Code esecuzione di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="7732d-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7732d-115">Note</span><span class="sxs-lookup"><span data-stu-id="7732d-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7732d-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="7732d-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7732d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7732d-117">Requirements</span></span>  
 <span data-ttu-id="7732d-118">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7732d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7732d-119">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7732d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7732d-120">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7732d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7732d-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7732d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7732d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7732d-122">See also</span></span>

- [<span data-ttu-id="7732d-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7732d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
