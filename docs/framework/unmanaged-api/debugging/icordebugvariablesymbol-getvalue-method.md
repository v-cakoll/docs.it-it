---
title: Metodo ICorDebugVariableSymbol::GetValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ede5c92a13ad12667d282cf53a7498683dccfb92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="aae57-102">Metodo ICorDebugVariableSymbol::GetValue</span><span class="sxs-lookup"><span data-stu-id="aae57-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="aae57-103">Ottiene il valore di una variabile come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="aae57-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae57-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aae57-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aae57-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aae57-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="aae57-106">[in] Offset iniziale nella variabile da cui leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="aae57-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="aae57-107">Questo parametro viene usato durante la lettura di campi membro in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="aae57-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="aae57-108">[in] Dimensioni in byte dell'argomento `context`.</span><span class="sxs-lookup"><span data-stu-id="aae57-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="aae57-109">[in] Contesto del thread usato per leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="aae57-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="aae57-110">[in] Dimensioni in byte del buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="aae57-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="aae57-111">[out] Numero di byte affettivamente scritti nel buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="aae57-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="aae57-112">[out] Matrice di byte contenente il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="aae57-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aae57-113">Note</span><span class="sxs-lookup"><span data-stu-id="aae57-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aae57-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="aae57-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae57-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aae57-115">Requirements</span></span>  
 <span data-ttu-id="aae57-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aae57-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae57-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="aae57-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aae57-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aae57-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aae57-119">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aae57-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae57-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aae57-120">See Also</span></span>  
 [<span data-ttu-id="aae57-121">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="aae57-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="aae57-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="aae57-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
