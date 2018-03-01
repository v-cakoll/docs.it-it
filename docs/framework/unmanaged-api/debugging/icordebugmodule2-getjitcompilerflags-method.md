---
title: Metodo ICorDebugModule2::GetJITCompilerFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25830b2d6ae7aedba0bb0ec0447d0b10605453eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="e0d4f-102">Metodo ICorDebugModule2::GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="e0d4f-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="e0d4f-103">Ottiene i flag che controllano la compilazione just-in-time (JIT) di questa interfaccia ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="e0d4f-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0d4f-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0d4f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0d4f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="e0d4f-106">[out] Un puntatore a un valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che controlla la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="e0d4f-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0d4f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0d4f-107">Requirements</span></span>  
 <span data-ttu-id="e0d4f-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0d4f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0d4f-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e0d4f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0d4f-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0d4f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0d4f-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0d4f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
