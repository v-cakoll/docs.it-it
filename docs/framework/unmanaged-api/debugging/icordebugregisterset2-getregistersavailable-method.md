---
title: Metodo ICorDebugRegisterSet2::GetRegistersAvailable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e2e3862f91fc68879e2f9e396ab9045c617de82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="941ba-102">Metodo ICorDebugRegisterSet2::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="941ba-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="941ba-103">Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="941ba-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="941ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="941ba-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="941ba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="941ba-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="941ba-106">[in] Dimensione della matrice `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="941ba-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="941ba-107">[out] Matrice di byte, ogni bit che corrisponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="941ba-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="941ba-108">Se un registro è disponibile, viene impostato il bit corrispondente.</span><span class="sxs-lookup"><span data-stu-id="941ba-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="941ba-109">Note</span><span class="sxs-lookup"><span data-stu-id="941ba-109">Remarks</span></span>  
 <span data-ttu-id="941ba-110">I valori dell'enumerazione CorDebugRegister specificano i registri di microprocessori diversi.</span><span class="sxs-lookup"><span data-stu-id="941ba-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="941ba-111">I cinque bit superiori di ogni valore sono l'indice di `availableRegChunks` matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="941ba-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="941ba-112">I tre bit inferiore di ogni valore di identificare la posizione del bit all'interno del byte indicizzato.</span><span class="sxs-lookup"><span data-stu-id="941ba-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="941ba-113">Dato un `CorDebugRegister` valore che specifica un particolare registro, la posizione del registro nella maschera è determinato come segue:</span><span class="sxs-lookup"><span data-stu-id="941ba-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="941ba-114">Estrarre necessaria per accedere al byte corretto in corrispondenza dell'indice di `availableRegChunks` matrice:</span><span class="sxs-lookup"><span data-stu-id="941ba-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="941ba-115">`CorDebugRegister`valore >> 3</span><span class="sxs-lookup"><span data-stu-id="941ba-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="941ba-116">Estrarre la posizione del bit all'interno del byte indicizzato, in bit zero è il bit meno significativo:</span><span class="sxs-lookup"><span data-stu-id="941ba-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="941ba-117">`CorDebugRegister`valore & 7</span><span class="sxs-lookup"><span data-stu-id="941ba-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="941ba-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="941ba-118">Requirements</span></span>  
 <span data-ttu-id="941ba-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="941ba-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="941ba-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="941ba-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="941ba-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="941ba-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="941ba-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="941ba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941ba-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="941ba-123">See Also</span></span>  
 [<span data-ttu-id="941ba-124">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="941ba-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="941ba-125">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="941ba-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
