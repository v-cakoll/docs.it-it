---
title: Metodo ICorDebugNativeFrame::GetRegisterSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7689632d41971d85417501e9a7f90712a07b34bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="4aa52-102">Metodo ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="4aa52-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="4aa52-103">Ottiene il set di registri di stack frame corrente.</span><span class="sxs-lookup"><span data-stu-id="4aa52-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aa52-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4aa52-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4aa52-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="4aa52-106">[out] Un puntatore all'indirizzo di un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) set di oggetti che rappresenta il registro per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="4aa52-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aa52-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4aa52-107">Requirements</span></span>  
 <span data-ttu-id="4aa52-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aa52-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aa52-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4aa52-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4aa52-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4aa52-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4aa52-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aa52-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa52-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aa52-112">See Also</span></span>  
 
