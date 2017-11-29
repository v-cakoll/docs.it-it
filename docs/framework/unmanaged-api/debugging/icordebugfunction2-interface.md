---
title: ICorDebugFunction2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2
helpviewer_keywords: ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c2806003e06d00a492568d1e2d86add66b5f0ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="95cee-102">ICorDebugFunction2 Interface1</span><span class="sxs-lookup"><span data-stu-id="95cee-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="95cee-103">Estende logicamente l'interfaccia ICorDebugFunction per fornire il supporto per il debug Just My Code passo a passo, che ignora il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="95cee-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95cee-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="95cee-104">Methods</span></span>  
  
|<span data-ttu-id="95cee-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="95cee-105">Method</span></span>|<span data-ttu-id="95cee-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95cee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95cee-107">EnumerateNativeCode (metodo)</span><span class="sxs-lookup"><span data-stu-id="95cee-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="95cee-108">(Non ancora implementato). Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="95cee-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="95cee-109">GetJMCStatus (metodo)</span><span class="sxs-lookup"><span data-stu-id="95cee-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="95cee-110">Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="95cee-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="95cee-111">GetVersionNumber (metodo)</span><span class="sxs-lookup"><span data-stu-id="95cee-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="95cee-112">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="95cee-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="95cee-113">SetJMCStatus (metodo)</span><span class="sxs-lookup"><span data-stu-id="95cee-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="95cee-114">Contrassegna questa funzione per Just My Code l'esecuzione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="95cee-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95cee-115">Note</span><span class="sxs-lookup"><span data-stu-id="95cee-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95cee-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="95cee-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95cee-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95cee-117">Requirements</span></span>  
 <span data-ttu-id="95cee-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95cee-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95cee-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="95cee-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95cee-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95cee-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95cee-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95cee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cee-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95cee-122">See Also</span></span>  
 [<span data-ttu-id="95cee-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="95cee-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
