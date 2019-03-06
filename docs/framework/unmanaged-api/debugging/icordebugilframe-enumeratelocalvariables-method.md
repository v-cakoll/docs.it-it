---
title: Metodo ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cc9601105d05740e6db0a41bae521bd9a276d74
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471316"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="7bbd4-102">Metodo ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="7bbd4-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="7bbd4-103">Ottiene un enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="7bbd4-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bbd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bbd4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bbd4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7bbd4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="7bbd4-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="7bbd4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bbd4-107">Note</span><span class="sxs-lookup"><span data-stu-id="7bbd4-107">Remarks</span></span>  
 <span data-ttu-id="7bbd4-108">`EnumerateLocalVariables` Ottiene un enumeratore in grado di elencare le variabili locali nel frame di chiamata che è rappresentato dall'oggetto ICorDebugILFrame disponibili.</span><span class="sxs-lookup"><span data-stu-id="7bbd4-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="7bbd4-109">L'elenco potrebbe non includere tutte le variabili locali nella funzione in esecuzione, poiché alcuni di essi potrebbero non essere attivo.</span><span class="sxs-lookup"><span data-stu-id="7bbd4-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bbd4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7bbd4-110">Requirements</span></span>  
 <span data-ttu-id="7bbd4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bbd4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bbd4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bbd4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bbd4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bbd4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bbd4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
