---
title: Metodo ICorDebugRegisterSet::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 40de06d47654337542d2c80dc325f8201335312a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379149"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="fa049-102">Metodo ICorDebugRegisterSet::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="fa049-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="fa049-103">Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="fa049-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa049-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa049-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa049-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa049-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="fa049-106">in Maschera di bit che specifica i valori di registro da recuperare.</span><span class="sxs-lookup"><span data-stu-id="fa049-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="fa049-107">Ogni bit corrisponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="fa049-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="fa049-108">Se un bit è impostato su uno, il valore del registro viene recuperato. in caso contrario, il valore del registro non viene recuperato.</span><span class="sxs-lookup"><span data-stu-id="fa049-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="fa049-109">in Numero di valori di registro da recuperare.</span><span class="sxs-lookup"><span data-stu-id="fa049-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="fa049-110">out Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve un valore di un registro.</span><span class="sxs-lookup"><span data-stu-id="fa049-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa049-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fa049-111">Remarks</span></span>  
 <span data-ttu-id="fa049-112">La dimensione della matrice deve essere uguale al numero di bit impostato su uno nella maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="fa049-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="fa049-113">Il `regCount` parametro specifica il numero di elementi nel buffer che riceveranno i valori del registro.</span><span class="sxs-lookup"><span data-stu-id="fa049-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="fa049-114">Se il `regCount` valore è troppo piccolo per il numero di registri indicato dalla maschera, i registri con numero più elevato verranno troncati dal set.</span><span class="sxs-lookup"><span data-stu-id="fa049-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="fa049-115">Se il `regCount` valore è troppo grande, gli elementi inutilizzati non `regBuffer` verranno modificati.</span><span class="sxs-lookup"><span data-stu-id="fa049-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="fa049-116">Se la maschera di bit specifica un registro non disponibile, `GetRegisters` restituisce un valore indeterminato per tale registro.</span><span class="sxs-lookup"><span data-stu-id="fa049-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa049-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa049-117">Requirements</span></span>  
 <span data-ttu-id="fa049-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa049-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa049-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa049-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa049-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa049-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa049-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa049-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa049-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa049-122">See also</span></span>

- [<span data-ttu-id="fa049-123">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="fa049-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="fa049-124">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="fa049-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
