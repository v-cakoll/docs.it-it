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
ms.openlocfilehash: cfd7ee890a7f2c3ea8cd3de9fbe830575c0ca10c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402774"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="b98c3-102">Metodo ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="b98c3-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="b98c3-103">Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b98c3-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b98c3-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b98c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b98c3-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="b98c3-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugBreakpointEnum che è l'enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b98c3-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b98c3-107">Note</span><span class="sxs-lookup"><span data-stu-id="b98c3-107">Remarks</span></span>  
 <span data-ttu-id="b98c3-108">L'enumeratore include tutti i tipi di punti di interruzione, inclusi i punti di interruzione di funzione e i punti di interruzione di dati.</span><span class="sxs-lookup"><span data-stu-id="b98c3-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98c3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b98c3-109">Requirements</span></span>  
 <span data-ttu-id="b98c3-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b98c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98c3-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b98c3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b98c3-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b98c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b98c3-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
