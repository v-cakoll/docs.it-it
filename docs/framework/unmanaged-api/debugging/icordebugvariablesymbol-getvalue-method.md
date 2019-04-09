---
title: Metodo ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186d9eec0aa6ad9e327b1dd4d0f19e251c79ecf9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147277"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="f1697-102">Metodo ICorDebugVariableSymbol::GetValue</span><span class="sxs-lookup"><span data-stu-id="f1697-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="f1697-103">Ottiene il valore di una variabile come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="f1697-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1697-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1697-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f1697-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1697-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f1697-106">[in] Offset iniziale nella variabile da cui leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="f1697-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="f1697-107">Questo parametro viene usato durante la lettura di campi membro in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f1697-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="f1697-108">[in] Dimensioni in byte dell'argomento `context`.</span><span class="sxs-lookup"><span data-stu-id="f1697-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="f1697-109">[in] Contesto del thread usato per leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="f1697-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="f1697-110">[in] Dimensioni in byte del buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f1697-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="f1697-111">[out] Numero di byte affettivamente scritti nel buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f1697-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f1697-112">[out] Matrice di byte contenente il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="f1697-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1697-113">Note</span><span class="sxs-lookup"><span data-stu-id="f1697-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1697-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f1697-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1697-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1697-115">Requirements</span></span>  
 <span data-ttu-id="f1697-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1697-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1697-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1697-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1697-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1697-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f1697-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f1697-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1697-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1697-120">See also</span></span>

- [<span data-ttu-id="f1697-121">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f1697-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f1697-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f1697-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
