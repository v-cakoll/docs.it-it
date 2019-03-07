---
title: Metodo ICorDebugAppDomain::EnumerateBreakpoints
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498341"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="5a522-102">Metodo ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="5a522-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="5a522-103">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a522-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a522-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a522-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a522-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a522-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="5a522-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugBreakpointEnum che è l'enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a522-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a522-107">Note</span><span class="sxs-lookup"><span data-stu-id="5a522-107">Remarks</span></span>  
 <span data-ttu-id="5a522-108">L'enumeratore include tutti i tipi di punti di interruzione, tra cui i punti di interruzione di funzione e i punti di interruzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="5a522-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a522-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a522-109">Requirements</span></span>  
 <span data-ttu-id="5a522-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a522-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a522-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a522-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a522-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a522-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a522-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a522-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
