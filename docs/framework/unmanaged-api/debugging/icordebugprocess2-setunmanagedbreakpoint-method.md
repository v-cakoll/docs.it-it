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
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178641"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="7bfee-102">Metodo ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7bfee-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="7bfee-103">Imposta un punto di interruzione non gestito in corrispondenza dell'offset dell'immagine nativa specificato.</span><span class="sxs-lookup"><span data-stu-id="7bfee-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bfee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bfee-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bfee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7bfee-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="7bfee-106">[in] Oggetto `CORDB_ADDRESS` che specifica l'offset dell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="7bfee-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="7bfee-107">[in] Dimensione, in byte, `buffer` della matrice.</span><span class="sxs-lookup"><span data-stu-id="7bfee-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7bfee-108">[fuori] Matrice che contiene il codice operativo sostituito dal punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="7bfee-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="7bfee-109">[fuori] Puntatore al numero di byte `buffer` restituiti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="7bfee-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bfee-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7bfee-110">Remarks</span></span>  
 <span data-ttu-id="7bfee-111">Se l'offset dell'immagine nativa si trova all'interno di Common Language Runtime (CLR), il punto di interruzione verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="7bfee-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="7bfee-112">Ciò consente a CLR di evitare di inviare un punto di interruzione fuori banda, quando il punto di interruzione viene impostato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="7bfee-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bfee-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7bfee-113">Requirements</span></span>  
 <span data-ttu-id="7bfee-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bfee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bfee-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bfee-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bfee-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bfee-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bfee-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bfee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
