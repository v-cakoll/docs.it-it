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
ms.openlocfilehash: 6880ed3a2519ad7d4a415e4fcc4510668a0852f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416706"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="fd14d-102">Metodo ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="fd14d-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="fd14d-103">Ottiene il set di registri di stack frame corrente.</span><span class="sxs-lookup"><span data-stu-id="fd14d-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd14d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd14d-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd14d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd14d-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="fd14d-106">[out] Un puntatore all'indirizzo di un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) set di oggetti che rappresenta il registro per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="fd14d-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd14d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd14d-107">Requirements</span></span>  
 <span data-ttu-id="fd14d-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd14d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd14d-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fd14d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd14d-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fd14d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd14d-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd14d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd14d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd14d-112">See Also</span></span>  
 
