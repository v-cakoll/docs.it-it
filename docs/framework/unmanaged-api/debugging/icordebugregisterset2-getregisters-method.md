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
ms.openlocfilehash: b7a356d80d63fae65191bbf4fc0a23d7e02004c9
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378224"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="20afa-102">Metodo ICorDebugRegisterSet2::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="20afa-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="20afa-103">Ottiene il valore di ogni registro (per la piattaforma in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit specificata.</span><span class="sxs-lookup"><span data-stu-id="20afa-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20afa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20afa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20afa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20afa-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="20afa-106">in Dimensione, in byte, della `mask` matrice.</span><span class="sxs-lookup"><span data-stu-id="20afa-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="20afa-107">in Matrice di byte, ogni bit corrispondente a un registro.</span><span class="sxs-lookup"><span data-stu-id="20afa-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="20afa-108">Se il bit è 1, verrà recuperato il valore del registro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="20afa-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="20afa-109">in Numero di valori di registro da recuperare.</span><span class="sxs-lookup"><span data-stu-id="20afa-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="20afa-110">out Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve il valore di un registro.</span><span class="sxs-lookup"><span data-stu-id="20afa-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20afa-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="20afa-111">Remarks</span></span>  
 <span data-ttu-id="20afa-112">Il `GetRegisters` metodo restituisce una matrice di valori dai registri specificati dalla maschera.</span><span class="sxs-lookup"><span data-stu-id="20afa-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="20afa-113">La matrice non contiene valori di registri il cui bit mask non è impostato.</span><span class="sxs-lookup"><span data-stu-id="20afa-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="20afa-114">Pertanto, le dimensioni della `regBuffer` matrice devono essere uguali al numero di 1 nella maschera.</span><span class="sxs-lookup"><span data-stu-id="20afa-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="20afa-115">Se il valore di `regCount` è troppo piccolo per il numero di registri indicato dalla maschera, i valori dei registri con numero superiore verranno troncati dal set.</span><span class="sxs-lookup"><span data-stu-id="20afa-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="20afa-116">Se `regCount` è troppo grande, gli elementi inutilizzati non `regBuffer` verranno modificati.</span><span class="sxs-lookup"><span data-stu-id="20afa-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="20afa-117">Se un registro non disponibile è indicato dalla maschera, viene restituito un valore indeterminato per tale registro.</span><span class="sxs-lookup"><span data-stu-id="20afa-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="20afa-118">Il `ICorDebugRegisterSet2::GetRegisters` metodo è necessario per le piattaforme con più di 64 registri.</span><span class="sxs-lookup"><span data-stu-id="20afa-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="20afa-119">Ad esempio, IA64 ha 128 registri per utilizzo generico e 128 registri a virgola mobile, quindi è necessario più di 64 bit nella maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="20afa-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="20afa-120">Se non si dispone di più di 64 registri, come nel caso di piattaforme come x86, il `GetRegisters` metodo converte in realtà solo i byte nella matrice di byte in `mask` un oggetto `ULONG64` e quindi chiama il metodo [ICorDebugRegisterSet:: GetRegisters](icordebugregisterset-getregisters-method.md) , che accetta la `ULONG64` maschera.</span><span class="sxs-lookup"><span data-stu-id="20afa-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20afa-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20afa-121">Requirements</span></span>  
 <span data-ttu-id="20afa-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20afa-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20afa-123">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20afa-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20afa-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20afa-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20afa-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20afa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20afa-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20afa-126">See also</span></span>

- [<span data-ttu-id="20afa-127">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="20afa-127">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="20afa-128">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="20afa-128">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
