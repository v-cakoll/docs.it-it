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
ms.openlocfilehash: 03a4f7ecc227679e6b0afa29b20de1aefeae3b76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077927"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="bba22-102">Metodo ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="bba22-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="bba22-103">Ottiene il set di registri di stack frame corrente.</span><span class="sxs-lookup"><span data-stu-id="bba22-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bba22-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bba22-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bba22-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="bba22-106">[out] Un puntatore all'indirizzo di un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) set di oggetti che rappresenta il registro per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="bba22-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bba22-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bba22-107">Requirements</span></span>  
 <span data-ttu-id="bba22-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bba22-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bba22-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bba22-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bba22-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bba22-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bba22-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bba22-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bba22-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bba22-112">See also</span></span>
