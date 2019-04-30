---
title: Metodo ICorDebugProcess2::SetUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b374720bd7bdad48222da006b809702de6462a62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948843"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="6f52e-102">Metodo ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6f52e-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="6f52e-103">Imposta un punto di interruzione non gestita in corrispondenza dell'offset di immagine nativa specificata.</span><span class="sxs-lookup"><span data-stu-id="6f52e-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f52e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f52e-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f52e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f52e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6f52e-106">[in] Oggetto `CORDB_ADDRESS` oggetto che specifica l'offset di immagini native.</span><span class="sxs-lookup"><span data-stu-id="6f52e-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="6f52e-107">[in] Le dimensioni, in byte, del `buffer` matrice.</span><span class="sxs-lookup"><span data-stu-id="6f52e-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="6f52e-108">[out] Matrice che contiene il codice operativo che viene sostituito dal punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="6f52e-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="6f52e-109">[out] Un puntatore al numero di byte restituiti nella `buffer` matrice.</span><span class="sxs-lookup"><span data-stu-id="6f52e-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f52e-110">Note</span><span class="sxs-lookup"><span data-stu-id="6f52e-110">Remarks</span></span>  
 <span data-ttu-id="6f52e-111">Se l'offset di immagini native è all'interno di common language runtime (CLR), il punto di interruzione verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="6f52e-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="6f52e-112">In questo modo la CLR evitare l'invio di un punto di interruzione, out-of-band quando è impostato il punto di interruzione dal debugger.</span><span class="sxs-lookup"><span data-stu-id="6f52e-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f52e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f52e-113">Requirements</span></span>  
 <span data-ttu-id="6f52e-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f52e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f52e-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f52e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f52e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f52e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f52e-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f52e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
