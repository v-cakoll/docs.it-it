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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4887d44f0ac5603280efa0abdbd7e65c71fc3ca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485454"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="f1ede-102">Metodo ICorDebugRegisterSet::GetRegisters</span><span class="sxs-lookup"><span data-stu-id="f1ede-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="f1ede-103">Ottiene il valore di ogni registro (nel computer che esegue codice) che viene specificato per la maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="f1ede-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ede-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1ede-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1ede-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1ede-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="f1ede-106">[in] Maschera di bit che specifica quale registro e i valori devono essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="f1ede-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="f1ede-107">Ogni bit corrisponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="f1ede-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="f1ede-108">Se un bit è impostato su uno, viene recuperato il valore del Registro; in caso contrario, non è possibile recuperare il valore del registro.</span><span class="sxs-lookup"><span data-stu-id="f1ede-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="f1ede-109">[in] Il numero di valori di registro da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f1ede-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="f1ede-110">[out] Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve un valore di un registro.</span><span class="sxs-lookup"><span data-stu-id="f1ede-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1ede-111">Note</span><span class="sxs-lookup"><span data-stu-id="f1ede-111">Remarks</span></span>  
 <span data-ttu-id="f1ede-112">Le dimensioni della matrice devono essere uguale al numero di bit impostati su uno nella maschera di bit.</span><span class="sxs-lookup"><span data-stu-id="f1ede-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="f1ede-113">Il `regCount` parametro specifica il numero di elementi nel buffer che riceverà i valori di registro.</span><span class="sxs-lookup"><span data-stu-id="f1ede-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="f1ede-114">Se il `regCount` valore è troppo piccolo per il numero di registri indicati dalla maschera, i registri numerati più alto verranno troncati dal set.</span><span class="sxs-lookup"><span data-stu-id="f1ede-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="f1ede-115">Se il `regCount` valore è troppo grande, inutilizzata `regBuffer` elementi saranno non modificati.</span><span class="sxs-lookup"><span data-stu-id="f1ede-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="f1ede-116">Se la maschera di bit specifica un registro che non è disponibile, `GetRegisters` restituisce un valore non definito per tale registro.</span><span class="sxs-lookup"><span data-stu-id="f1ede-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ede-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1ede-117">Requirements</span></span>  
 <span data-ttu-id="f1ede-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ede-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ede-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1ede-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1ede-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ede-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ede-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ede-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ede-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1ede-122">See also</span></span>
- [<span data-ttu-id="f1ede-123">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="f1ede-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="f1ede-124">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="f1ede-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
