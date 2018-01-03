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
ms.workload: dotnet
ms.openlocfilehash: 7ac3a4cd5ec2aff1b60cd51ca33d411e5cc81eb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="98edc-102">ICorDebugFunction2 Interface1</span><span class="sxs-lookup"><span data-stu-id="98edc-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="98edc-103">Estende logicamente l'interfaccia ICorDebugFunction per fornire il supporto per il debug Just My Code passo a passo, che ignora il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="98edc-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98edc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="98edc-104">Methods</span></span>  
  
|<span data-ttu-id="98edc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="98edc-105">Method</span></span>|<span data-ttu-id="98edc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98edc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98edc-107">Metodo EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="98edc-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="98edc-108">(Non ancora implementato). Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="98edc-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="98edc-109">Metodo GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="98edc-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="98edc-110">Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="98edc-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="98edc-111">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="98edc-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="98edc-112">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="98edc-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="98edc-113">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="98edc-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="98edc-114">Contrassegna questa funzione per Just My Code l'esecuzione di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="98edc-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98edc-115">Note</span><span class="sxs-lookup"><span data-stu-id="98edc-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98edc-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="98edc-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98edc-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98edc-117">Requirements</span></span>  
 <span data-ttu-id="98edc-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98edc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98edc-119">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="98edc-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98edc-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98edc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98edc-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98edc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98edc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98edc-122">See Also</span></span>  
 [<span data-ttu-id="98edc-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="98edc-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
