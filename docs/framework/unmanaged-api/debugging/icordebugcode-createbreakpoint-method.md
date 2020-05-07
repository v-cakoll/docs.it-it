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
ms.openlocfilehash: 40582b1289875d5151ea96e3153c6e4760737e84
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893805"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="230c2-102">Metodo ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="230c2-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="230c2-103">Crea un punto di interruzione in questo segmento di codice in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="230c2-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="230c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="230c2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="230c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="230c2-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="230c2-106">in Offset in corrispondenza del quale creare il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="230c2-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="230c2-107">out Puntatore all'indirizzo di un oggetto "ICorDebugFunctionBreakpoint" che rappresenta il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="230c2-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="230c2-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="230c2-108">Remarks</span></span>  
 <span data-ttu-id="230c2-109">Prima che il punto di interruzione sia attivo, è necessario aggiungerlo all'oggetto processo.</span><span class="sxs-lookup"><span data-stu-id="230c2-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="230c2-110">Se questo codice è codice MSIL (Microsoft Intermediate Language) ed è presente una versione nativa del codice compilata JIT (just-in-Time), il punto di interruzione verrà applicato anche nel codice compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="230c2-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="230c2-111">(Lo stesso vale se il codice viene compilato in modalità JIT in un secondo momento).</span><span class="sxs-lookup"><span data-stu-id="230c2-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="230c2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="230c2-112">Requirements</span></span>  
 <span data-ttu-id="230c2-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="230c2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="230c2-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="230c2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="230c2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="230c2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="230c2-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="230c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
