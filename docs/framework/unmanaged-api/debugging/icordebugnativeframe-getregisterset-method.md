---
title: Metodo ICorDebugNativeFrame::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18db366bde4211afa0f65052affa0ab9639df122
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498926"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="28375-102">Metodo ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="28375-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="28375-103">Ottiene il set di registri di stack frame corrente.</span><span class="sxs-lookup"><span data-stu-id="28375-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28375-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28375-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28375-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="28375-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="28375-106">[out] Un puntatore all'indirizzo di un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) set di oggetti che rappresenta il registro per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="28375-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28375-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28375-107">Requirements</span></span>  
 <span data-ttu-id="28375-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28375-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28375-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28375-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28375-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28375-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28375-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28375-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28375-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28375-112">See also</span></span>

