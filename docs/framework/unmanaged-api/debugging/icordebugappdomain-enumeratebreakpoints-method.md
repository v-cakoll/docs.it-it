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
ms.openlocfilehash: 3611684a17d51fc4fdba31dd4049540039b43e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110511"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="c2d79-102">Metodo ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="c2d79-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="c2d79-103">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2d79-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2d79-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2d79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2d79-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="c2d79-106">out Puntatore all'indirizzo di un oggetto ICorDebugBreakpointEnum che rappresenta l'enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2d79-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2d79-107">Note</span><span class="sxs-lookup"><span data-stu-id="c2d79-107">Remarks</span></span>  
 <span data-ttu-id="c2d79-108">L'enumeratore include tutti i tipi di punti di interruzione, inclusi i punti di interruzione delle funzioni e i punti di interruzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c2d79-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2d79-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2d79-109">Requirements</span></span>  
 <span data-ttu-id="c2d79-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2d79-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d79-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2d79-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2d79-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2d79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2d79-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
