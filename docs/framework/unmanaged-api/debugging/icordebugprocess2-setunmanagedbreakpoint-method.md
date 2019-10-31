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
ms.openlocfilehash: ffab2762fd86e95c3272ca456039028e0897bc41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137176"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="4b75b-102">Metodo ICorDebugProcess2::SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4b75b-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="4b75b-103">Imposta un punto di interruzione non gestito in corrispondenza dell'offset dell'immagine nativa specificato.</span><span class="sxs-lookup"><span data-stu-id="4b75b-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b75b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b75b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b75b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b75b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="4b75b-106">in Oggetto `CORDB_ADDRESS` che specifica l'offset dell'immagine nativa.</span><span class="sxs-lookup"><span data-stu-id="4b75b-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="4b75b-107">in Dimensione, in byte, della matrice `buffer`.</span><span class="sxs-lookup"><span data-stu-id="4b75b-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="4b75b-108">out Matrice che contiene il codice operativo che viene sostituito dal punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="4b75b-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="4b75b-109">out Puntatore al numero di byte restituiti nella matrice `buffer`.</span><span class="sxs-lookup"><span data-stu-id="4b75b-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b75b-110">Note</span><span class="sxs-lookup"><span data-stu-id="4b75b-110">Remarks</span></span>  
 <span data-ttu-id="4b75b-111">Se l'offset dell'immagine nativa si trova all'interno del Common Language Runtime (CLR), il punto di interruzione verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="4b75b-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="4b75b-112">Questo consente a CLR di evitare l'invio di un punto di interruzione fuori banda, quando il punto di interruzione viene impostato dal debugger.</span><span class="sxs-lookup"><span data-stu-id="4b75b-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b75b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b75b-113">Requirements</span></span>  
 <span data-ttu-id="4b75b-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b75b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b75b-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b75b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b75b-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b75b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b75b-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b75b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
