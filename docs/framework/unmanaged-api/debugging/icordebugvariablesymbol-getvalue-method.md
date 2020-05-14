---
title: Metodo ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: f217f7226d53a27363f66eb90a340fd3604a0217
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396511"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="966bf-102">Metodo ICorDebugVariableSymbol::GetValue</span><span class="sxs-lookup"><span data-stu-id="966bf-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="966bf-103">Ottiene il valore di una variabile come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="966bf-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="966bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="966bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="966bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="966bf-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="966bf-106">[in] Offset iniziale nella variabile da cui leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="966bf-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="966bf-107">Questo parametro viene usato durante la lettura di campi membro in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="966bf-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="966bf-108">[in] Dimensioni in byte dell'argomento `context`.</span><span class="sxs-lookup"><span data-stu-id="966bf-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="966bf-109">[in] Contesto del thread usato per leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="966bf-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="966bf-110">[in] Dimensioni in byte del buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="966bf-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="966bf-111">[out] Numero di byte affettivamente scritti nel buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="966bf-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="966bf-112">[out] Matrice di byte contenente il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="966bf-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="966bf-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="966bf-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="966bf-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="966bf-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="966bf-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="966bf-115">Requirements</span></span>  
 <span data-ttu-id="966bf-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="966bf-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="966bf-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="966bf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="966bf-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="966bf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="966bf-119">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="966bf-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="966bf-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="966bf-120">See also</span></span>

- [<span data-ttu-id="966bf-121">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="966bf-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="966bf-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="966bf-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
