---
title: Metodo ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b622d1bd82e53d5fa232e07b1f49e6fbba3ccba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414841"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="ef9fd-102">Metodo ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="ef9fd-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="ef9fd-103">Ottiene la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef9fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef9fd-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef9fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef9fd-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="ef9fd-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFunction che rappresenta la funzione contenente il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef9fd-107">Note</span><span class="sxs-lookup"><span data-stu-id="ef9fd-107">Remarks</span></span>  
 <span data-ttu-id="ef9fd-108">Il `GetFunction` metodo potrebbe non riuscire se il frame non è associato ad alcuna funzione particolare.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef9fd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef9fd-109">Requirements</span></span>  
 <span data-ttu-id="ef9fd-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef9fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef9fd-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ef9fd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef9fd-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ef9fd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef9fd-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef9fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
