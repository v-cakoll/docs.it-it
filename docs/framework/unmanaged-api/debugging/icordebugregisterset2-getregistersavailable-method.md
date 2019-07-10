---
title: Metodo ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4ab49aaccd77fac497bd86413915e82c99ed3e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744902"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="869d9-102">Metodo ICorDebugRegisterSet2::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="869d9-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="869d9-103">Ottiene una matrice di byte che fornisce una bitmap di registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="869d9-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="869d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="869d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="869d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="869d9-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="869d9-106">[in] Dimensione della matrice `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="869d9-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="869d9-107">[out] Matrice di byte, ogni bit che corrisponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="869d9-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="869d9-108">Se è disponibile un registro, viene impostato il bit corrispondente.</span><span class="sxs-lookup"><span data-stu-id="869d9-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="869d9-109">Note</span><span class="sxs-lookup"><span data-stu-id="869d9-109">Remarks</span></span>  
 <span data-ttu-id="869d9-110">I valori dell'enumerazione CorDebugRegister specificano i registri di microprocessori diversi.</span><span class="sxs-lookup"><span data-stu-id="869d9-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="869d9-111">I cinque bit superiore di ogni valore sono l'indice nel `availableRegChunks` matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="869d9-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="869d9-112">I tre bit inferiore di ogni valore di identificare la posizione del bit all'interno del byte indicizzata.</span><span class="sxs-lookup"><span data-stu-id="869d9-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="869d9-113">Dato un `CorDebugRegister` valore che specifica un determinato registro, la posizione del registro nella maschera è determinato come segue:</span><span class="sxs-lookup"><span data-stu-id="869d9-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="869d9-114">Estrarre necessaria per accedere al corretto byte in corrispondenza dell'indice di `availableRegChunks` matrice:</span><span class="sxs-lookup"><span data-stu-id="869d9-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="869d9-115">`CorDebugRegister` valore >> 3</span><span class="sxs-lookup"><span data-stu-id="869d9-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="869d9-116">Estrarre la posizione del bit all'interno del byte indicizzata, in cui il bit zero è il bit meno significativo:</span><span class="sxs-lookup"><span data-stu-id="869d9-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="869d9-117">`CorDebugRegister` valore di & amp;7</span><span class="sxs-lookup"><span data-stu-id="869d9-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="869d9-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="869d9-118">Requirements</span></span>  
 <span data-ttu-id="869d9-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="869d9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="869d9-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="869d9-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="869d9-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="869d9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="869d9-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="869d9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869d9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="869d9-123">See also</span></span>

- [<span data-ttu-id="869d9-124">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="869d9-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="869d9-125">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="869d9-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
