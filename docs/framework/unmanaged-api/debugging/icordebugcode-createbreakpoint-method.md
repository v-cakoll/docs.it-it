---
title: Metodo ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d193f9aa4d051baa73944545d28a455495aeda40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185770"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="577b5-102">Metodo ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="577b5-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="577b5-103">Crea un punto di interruzione in questo segmento di codice in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="577b5-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="577b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="577b5-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="577b5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="577b5-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="577b5-106">[in] Offset da cui creare il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="577b5-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="577b5-107">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugFunctionBreakpoint" che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="577b5-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="577b5-108">Note</span><span class="sxs-lookup"><span data-stu-id="577b5-108">Remarks</span></span>  
 <span data-ttu-id="577b5-109">Prima che il punto di interruzione è attivo, è necessario aggiungerlo all'oggetto processo.</span><span class="sxs-lookup"><span data-stu-id="577b5-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="577b5-110">Se questo codice è codice Microsoft intermediate language (MSIL) e vi è un just-in-time (JIT)-versione nativa compilata del codice, il punto di interruzione verrà applicati anche il codice compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="577b5-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="577b5-111">(Lo stesso vale se il codice viene compilato tramite JIT in un secondo momento.)</span><span class="sxs-lookup"><span data-stu-id="577b5-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="577b5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="577b5-112">Requirements</span></span>  
 <span data-ttu-id="577b5-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="577b5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="577b5-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="577b5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="577b5-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="577b5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="577b5-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="577b5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577b5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="577b5-117">See also</span></span>
