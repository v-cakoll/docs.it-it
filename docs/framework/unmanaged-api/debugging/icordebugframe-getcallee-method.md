---
title: Metodo ICorDebugFrame::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d62f4f8a34123bcd3f0cbe56f1c1b958bcaa6ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413372"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="ce0a2-102">Metodo ICorDebugFrame::GetCallee</span><span class="sxs-lookup"><span data-stu-id="ce0a2-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="ce0a2-103">Ottiene un puntatore all'oggetto ICorDebugFrame nella catena che ha chiamato il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="ce0a2-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce0a2-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce0a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce0a2-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="ce0a2-106">[out] Un puntatore all'indirizzo di un `ICorDebugFrame` oggetto che rappresenta il frame chiamato.</span><span class="sxs-lookup"><span data-stu-id="ce0a2-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="ce0a2-107">Questo valore è null se il frame del chiamante è il più interno nella catena corrente.</span><span class="sxs-lookup"><span data-stu-id="ce0a2-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce0a2-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce0a2-108">Requirements</span></span>  
 <span data-ttu-id="ce0a2-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce0a2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce0a2-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ce0a2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce0a2-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ce0a2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce0a2-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce0a2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
