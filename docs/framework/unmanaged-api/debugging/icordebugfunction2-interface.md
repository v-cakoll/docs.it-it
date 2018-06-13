---
title: ICorDebugFunction2 Interface1
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
ms.openlocfilehash: d765f87e36c98b5f664e84d85b883bc949fccf54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415334"
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="6ae9d-102">ICorDebugFunction2 Interface1</span><span class="sxs-lookup"><span data-stu-id="6ae9d-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="6ae9d-103">Estende logicamente l'interfaccia ICorDebugFunction per fornire il supporto per il debug Just My Code passo a passo, che ignora il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="6ae9d-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ae9d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6ae9d-104">Methods</span></span>  
  
|<span data-ttu-id="6ae9d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6ae9d-105">Method</span></span>|<span data-ttu-id="6ae9d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ae9d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ae9d-107">Metodo EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="6ae9d-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="6ae9d-108">(Non ancora implementato). Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="6ae9d-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="6ae9d-109">Metodo GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="6ae9d-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="6ae9d-110">Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="6ae9d-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="6ae9d-111">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="6ae9d-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="6ae9d-112">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="6ae9d-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="6ae9d-113">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="6ae9d-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="6ae9d-114">Contrassegna questa funzione per Just My Code l'esecuzione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="6ae9d-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ae9d-115">Note</span><span class="sxs-lookup"><span data-stu-id="6ae9d-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ae9d-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6ae9d-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ae9d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ae9d-117">Requirements</span></span>  
 <span data-ttu-id="6ae9d-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ae9d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ae9d-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6ae9d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ae9d-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6ae9d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ae9d-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ae9d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae9d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ae9d-122">See Also</span></span>  
 [<span data-ttu-id="6ae9d-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6ae9d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
