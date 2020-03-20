---
title: Metodo ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: a0b77724a5a70461073d554a9794c5a904f6a363
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178576"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="0d52a-102">Metodo ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="0d52a-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="0d52a-103">Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.</span><span class="sxs-lookup"><span data-stu-id="0d52a-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d52a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d52a-104">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d52a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d52a-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="0d52a-106">[in] Un puntatore a una matrice di byte da un evento di debug per le eccezioni native che include informazioni relative a un evento di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="0d52a-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="0d52a-107">[in] Il numero di elementi nella matrice di byte `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="0d52a-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="0d52a-108">[in] Membro di enumerazione [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) che specifica il formato dell'evento di debug non gestito.</span><span class="sxs-lookup"><span data-stu-id="0d52a-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0d52a-109">[in] Un campo di bit che dipende dall'architettura di destinazione e che fornisce informazioni aggiuntive relative all'evento di debug.</span><span class="sxs-lookup"><span data-stu-id="0d52a-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="0d52a-110">Per i sistemi Windows, può essere un membro dell'enumerazione [CorDebugDecodeEventFlagsWindows.](cordebugdecodeeventflagswindows-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="0d52a-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="0d52a-111">[in] L'identificatore del sistema operativo del thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d52a-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="0d52a-112">[fuori] Puntatore all'indirizzo di un oggetto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) che rappresenta un evento di debug gestito decodificato.</span><span class="sxs-lookup"><span data-stu-id="0d52a-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d52a-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0d52a-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d52a-114">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0d52a-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d52a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d52a-115">Requirements</span></span>  
 <span data-ttu-id="0d52a-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d52a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d52a-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d52a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d52a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d52a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d52a-119">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d52a-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d52a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d52a-120">See also</span></span>

- [<span data-ttu-id="0d52a-121">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="0d52a-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="0d52a-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0d52a-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
