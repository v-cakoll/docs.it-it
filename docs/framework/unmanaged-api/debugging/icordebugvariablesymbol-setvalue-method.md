---
title: Metodo ICorDebugVariableSymbol::SetValue
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bfbadc5553e86b2db10d66298c8d24d2a0f8bde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211575"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="f3a74-102">Metodo ICorDebugVariableSymbol::SetValue</span><span class="sxs-lookup"><span data-stu-id="f3a74-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="f3a74-103">Assegna il valore di una matrice di byte a una variabile.</span><span class="sxs-lookup"><span data-stu-id="f3a74-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3a74-104">Syntax</span></span>  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3a74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3a74-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f3a74-106">[in] Offset iniziale nella variabile da cui leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="f3a74-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="f3a74-107">Questo parametro viene usato durante la scrittura nei campi membro di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f3a74-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="f3a74-108">[in] Identificatore del thread il cui contesto deve essere aggiornato per riflettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="f3a74-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="f3a74-109">[in] Dimensioni in byte del contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="f3a74-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="f3a74-110">[in] Contesto del thread usato per scrivere il valore.</span><span class="sxs-lookup"><span data-stu-id="f3a74-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="f3a74-111">[in] Dimensioni in byte del buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f3a74-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f3a74-112">[in] Buffer contenente il valore da configurare.</span><span class="sxs-lookup"><span data-stu-id="f3a74-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3a74-113">Note</span><span class="sxs-lookup"><span data-stu-id="f3a74-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3a74-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3a74-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a74-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3a74-115">Requirements</span></span>  
 <span data-ttu-id="f3a74-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3a74-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a74-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3a74-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3a74-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3a74-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f3a74-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f3a74-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f3a74-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3a74-120">See also</span></span>

- [<span data-ttu-id="f3a74-121">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f3a74-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f3a74-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f3a74-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
