---
title: Metodo ICorDebugProcess6::DecodeEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 753dce06d9481165bd2f0f1e49fe3c50fc6b3c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="0c8da-102">Metodo ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="0c8da-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="0c8da-103">Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.</span><span class="sxs-lookup"><span data-stu-id="0c8da-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c8da-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c8da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c8da-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="0c8da-106">[in] Un puntatore a una matrice di byte da un evento di debug per le eccezioni native che include informazioni relative a un evento di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="0c8da-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="0c8da-107">[in] Il numero di elementi nella matrice di byte `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="0c8da-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="0c8da-108">[in] Oggetto [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) membro di enumerazione che specifica il formato dell'evento di debug non gestito.</span><span class="sxs-lookup"><span data-stu-id="0c8da-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0c8da-109">[in] Un campo di bit che dipende dall'architettura di destinazione e che fornisce informazioni aggiuntive relative all'evento di debug.</span><span class="sxs-lookup"><span data-stu-id="0c8da-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="0c8da-110">Per i sistemi Windows, può essere un membro del [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0c8da-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="0c8da-111">[in] L'identificatore del sistema operativo del thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0c8da-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="0c8da-112">[out] Un puntatore all'indirizzo di un [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) oggetto che rappresenta un evento di debug gestito decodificato.</span><span class="sxs-lookup"><span data-stu-id="0c8da-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c8da-113">Note</span><span class="sxs-lookup"><span data-stu-id="0c8da-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c8da-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0c8da-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c8da-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c8da-115">Requirements</span></span>  
 <span data-ttu-id="0c8da-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c8da-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c8da-117">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0c8da-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c8da-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c8da-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c8da-119">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c8da-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8da-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c8da-120">See Also</span></span>  
 [<span data-ttu-id="0c8da-121">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="0c8da-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="0c8da-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0c8da-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
