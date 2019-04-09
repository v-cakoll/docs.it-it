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
ms.openlocfilehash: 159cebc76f732629ed84a3b6c9041cc15f8bbb69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199375"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="d92db-102">Interfaccia ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="d92db-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="d92db-103">Estende logicamente l'interfaccia ICorDebugFunction per fornire supporto per Just My Code debug passo-passo, che ignora il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="d92db-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d92db-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d92db-104">Methods</span></span>  
  
|<span data-ttu-id="d92db-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d92db-105">Method</span></span>|<span data-ttu-id="d92db-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d92db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d92db-107">Metodo EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="d92db-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="d92db-108">(Non ancora implementato). Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum contenente le istruzioni di codice nativo nella funzione di cui viene fatto riferimento dall'oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="d92db-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="d92db-109">Metodo GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="d92db-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="d92db-110">Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="d92db-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="d92db-111">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="d92db-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="d92db-112">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="d92db-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="d92db-113">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="d92db-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="d92db-114">Contrassegna questa funzione per Just My Code l'esecuzione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d92db-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d92db-115">Note</span><span class="sxs-lookup"><span data-stu-id="d92db-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d92db-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d92db-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d92db-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d92db-117">Requirements</span></span>  
 <span data-ttu-id="d92db-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d92db-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d92db-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d92db-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d92db-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d92db-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d92db-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d92db-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d92db-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d92db-122">See also</span></span>

- [<span data-ttu-id="d92db-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d92db-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
