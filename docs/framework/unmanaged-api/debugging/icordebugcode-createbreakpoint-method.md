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
ms.openlocfilehash: 1ec7d615b99ac301948d7ea25318115713ce06ea
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700847"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="6592f-102">Metodo ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6592f-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="6592f-103">Crea un punto di interruzione in questo segmento di codice in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="6592f-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6592f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6592f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6592f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6592f-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="6592f-106">in Offset in corrispondenza del quale creare il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="6592f-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="6592f-107">out Puntatore all'indirizzo di un oggetto "ICorDebugFunctionBreakpoint" che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="6592f-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6592f-108">Note</span><span class="sxs-lookup"><span data-stu-id="6592f-108">Remarks</span></span>  
 <span data-ttu-id="6592f-109">Prima che il punto di interruzione sia attivo, è necessario aggiungerlo all'oggetto processo.</span><span class="sxs-lookup"><span data-stu-id="6592f-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="6592f-110">Se questo codice è codice MSIL (Microsoft Intermediate Language) ed è presente una versione nativa del codice compilata JIT (just-in-Time), il punto di interruzione verrà applicato anche nel codice compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="6592f-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="6592f-111">(Lo stesso vale se il codice viene compilato in modalità JIT in un secondo momento).</span><span class="sxs-lookup"><span data-stu-id="6592f-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6592f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6592f-112">Requirements</span></span>  
 <span data-ttu-id="6592f-113">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6592f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6592f-114">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6592f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6592f-115">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6592f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6592f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6592f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
