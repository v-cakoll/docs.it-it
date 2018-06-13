---
title: Metodo ICorDebugRegisterSet2::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aca83a66520531074f376a47a7f2994cda237f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423234"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="caa1c-102">Metodo ICorDebugRegisterSet2::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="caa1c-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="caa1c-103">Ottiene il valore di ogni registro (per la piattaforma su cui è attualmente in esecuzione codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="caa1c-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa1c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="caa1c-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="caa1c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="caa1c-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="caa1c-106">[in] Le dimensioni, in byte, del `mask` matrice.</span><span class="sxs-lookup"><span data-stu-id="caa1c-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="caa1c-107">[in] Matrice di byte, ogni bit che corrisponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="caa1c-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="caa1c-108">Se il bit è 1, verrà recuperato il valore del registro corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="caa1c-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="caa1c-109">[in] Il numero di valori del registro da recuperare.</span><span class="sxs-lookup"><span data-stu-id="caa1c-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="caa1c-110">[out] Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve il valore di un registro.</span><span class="sxs-lookup"><span data-stu-id="caa1c-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caa1c-111">Note</span><span class="sxs-lookup"><span data-stu-id="caa1c-111">Remarks</span></span>  
 <span data-ttu-id="caa1c-112">Il `GetRegisters` metodo restituisce una matrice di valori dai registri specificati dalla maschera.</span><span class="sxs-lookup"><span data-stu-id="caa1c-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="caa1c-113">La matrice non contiene valori dei registri con maschera bit non è impostato.</span><span class="sxs-lookup"><span data-stu-id="caa1c-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="caa1c-114">Di conseguenza, le dimensioni del `regBuffer` matrice deve essere uguale al numero di 1 nella maschera.</span><span class="sxs-lookup"><span data-stu-id="caa1c-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="caa1c-115">Se il valore di `regCount` è troppo piccolo per il numero di registri indicato dalla maschera, i valori dei registri con numero maggiore verrà troncato dal set.</span><span class="sxs-lookup"><span data-stu-id="caa1c-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="caa1c-116">Se `regCount` è troppo grande, inutilizzata `regBuffer` gli elementi verranno modificati.</span><span class="sxs-lookup"><span data-stu-id="caa1c-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="caa1c-117">Se un registro non disponibile viene indicato dalla maschera, verrà restituito un valore indeterminato per tale registro.</span><span class="sxs-lookup"><span data-stu-id="caa1c-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="caa1c-118">Il `ICorDebugRegisterSet2::GetRegisters` metodo è necessario per le piattaforme che hanno più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="caa1c-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="caa1c-119">Ad esempio, IA64 ha 128 registri di uso generale e 128 registri a virgola mobile, pertanto è necessario più di 64-bit nella maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="caa1c-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="caa1c-120">Se non si dispone più di 64 registri, come nel caso di piattaforme, ad esempio x86, il `GetRegisters` metodo converte semplicemente i byte di `mask` matrice di byte in un `ULONG64` e quindi chiama il [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) metodo, che accetta il `ULONG64` mask.</span><span class="sxs-lookup"><span data-stu-id="caa1c-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa1c-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="caa1c-121">Requirements</span></span>  
 <span data-ttu-id="caa1c-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa1c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa1c-123">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="caa1c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caa1c-124">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="caa1c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caa1c-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa1c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa1c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caa1c-126">See Also</span></span>  
 [<span data-ttu-id="caa1c-127">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="caa1c-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="caa1c-128">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="caa1c-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
