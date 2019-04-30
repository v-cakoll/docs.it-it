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
ms.openlocfilehash: 82902e6a395fe62464065ccea4cca5b52c960f0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988813"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="3e27d-102">Metodo ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="3e27d-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="3e27d-103">Ottiene un puntatore all'oggetto ICorDebugFrame nella catena che ha chiamato il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="3e27d-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e27d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e27d-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e27d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e27d-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="3e27d-106">[out] Un puntatore all'indirizzo di un `ICorDebugFrame` oggetto che rappresenta il frame di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e27d-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="3e27d-107">Questo valore è null se il frame di chiamata è il frame più esterno nella catena di corrente.</span><span class="sxs-lookup"><span data-stu-id="3e27d-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e27d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e27d-108">Requirements</span></span>  
 <span data-ttu-id="3e27d-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e27d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e27d-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e27d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e27d-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e27d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e27d-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e27d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
