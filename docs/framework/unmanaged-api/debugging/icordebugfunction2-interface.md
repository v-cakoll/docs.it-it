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
ms.openlocfilehash: 5364e39f7e0a9b6c9cd10cd8f17bab4a03a4b7af
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794487"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="d85b0-102">Interfaccia ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="d85b0-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="d85b0-103">Estende logicamente l'interfaccia ICorDebugFunction per fornire supporto per Just My Code il debug step-through, che ignora il codice non utente.</span><span class="sxs-lookup"><span data-stu-id="d85b0-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d85b0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d85b0-104">Methods</span></span>  
  
|<span data-ttu-id="d85b0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d85b0-105">Method</span></span>|<span data-ttu-id="d85b0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d85b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d85b0-107">Metodo EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="d85b0-107">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="d85b0-108">(Non ancora implementato). Ottiene un puntatore a interfaccia a un ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="d85b0-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="d85b0-109">Metodo GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="d85b0-109">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="d85b0-110">Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.</span><span class="sxs-lookup"><span data-stu-id="d85b0-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="d85b0-111">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="d85b0-111">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="d85b0-112">Ottiene la versione di modifica e continuazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="d85b0-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="d85b0-113">Metodo SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="d85b0-113">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="d85b0-114">Contrassegna questa funzione per Just My Code esecuzione di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d85b0-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d85b0-115">Note</span><span class="sxs-lookup"><span data-stu-id="d85b0-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d85b0-116">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d85b0-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d85b0-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d85b0-117">Requirements</span></span>  
 <span data-ttu-id="d85b0-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d85b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d85b0-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d85b0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d85b0-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d85b0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d85b0-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d85b0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85b0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d85b0-122">See also</span></span>

- [<span data-ttu-id="d85b0-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d85b0-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
