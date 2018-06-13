---
title: Metodo ICorDebugFrame::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2452f4be0acde300676bf56011416e0a9ef16464
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411716"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="9db5c-102">Metodo ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="9db5c-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="9db5c-103">Ottiene un puntatore all'oggetto ICorDebugFrame nella catena che ha chiamato il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="9db5c-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9db5c-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9db5c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9db5c-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="9db5c-106">[out] Un puntatore all'indirizzo di un `ICorDebugFrame` oggetto che rappresenta il frame del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9db5c-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="9db5c-107">Questo valore è null se il frame chiamato cornice più esterna della catena corrente.</span><span class="sxs-lookup"><span data-stu-id="9db5c-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9db5c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9db5c-108">Requirements</span></span>  
 <span data-ttu-id="9db5c-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9db5c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db5c-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9db5c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9db5c-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9db5c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9db5c-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9db5c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
