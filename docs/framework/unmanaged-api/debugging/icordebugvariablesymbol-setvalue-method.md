---
title: Metodo ICorDebugVariableSymbol::SetValue
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: fe6b63e4c0706dd69478753b3512f606e73bee7c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790859"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="6efdd-102">Metodo ICorDebugVariableSymbol::SetValue</span><span class="sxs-lookup"><span data-stu-id="6efdd-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="6efdd-103">Assegna il valore di una matrice di byte a una variabile.</span><span class="sxs-lookup"><span data-stu-id="6efdd-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6efdd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6efdd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6efdd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6efdd-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="6efdd-106">[in] Offset iniziale nella variabile da cui leggere il valore.</span><span class="sxs-lookup"><span data-stu-id="6efdd-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="6efdd-107">Questo parametro viene usato durante la scrittura nei campi membro di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="6efdd-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="6efdd-108">[in] Identificatore del thread il cui contesto deve essere aggiornato per riflettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="6efdd-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="6efdd-109">[in] Dimensioni in byte del contesto del thread.</span><span class="sxs-lookup"><span data-stu-id="6efdd-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="6efdd-110">[in] Contesto del thread usato per scrivere il valore.</span><span class="sxs-lookup"><span data-stu-id="6efdd-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="6efdd-111">[in] Dimensioni in byte del buffer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="6efdd-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6efdd-112">[in] Buffer contenente il valore da configurare.</span><span class="sxs-lookup"><span data-stu-id="6efdd-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6efdd-113">Note</span><span class="sxs-lookup"><span data-stu-id="6efdd-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6efdd-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6efdd-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6efdd-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6efdd-115">Requirements</span></span>  
 <span data-ttu-id="6efdd-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6efdd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6efdd-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6efdd-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6efdd-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6efdd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6efdd-119">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6efdd-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efdd-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6efdd-120">See also</span></span>

- [<span data-ttu-id="6efdd-121">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="6efdd-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="6efdd-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6efdd-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
