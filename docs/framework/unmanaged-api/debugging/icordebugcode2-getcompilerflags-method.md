---
title: Metodo ICorDebugCode2::GetCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4733d59eb14f736f1369de82a7e9c677a65c3f86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093644"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="15682-102">Metodo ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="15682-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="15682-103">Ottiene i flag che specificano le condizioni in cui questo oggetto di codice è stato entrambi just-in-time (JIT) compilate o generate usando il generatore di immagini native (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="15682-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15682-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15682-104">Syntax</span></span>  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15682-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15682-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="15682-106">[out] Un puntatore a un valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che specifica il comportamento del compilatore JIT o il generatore di immagini native.</span><span class="sxs-lookup"><span data-stu-id="15682-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15682-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15682-107">Requirements</span></span>  
 <span data-ttu-id="15682-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15682-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15682-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15682-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15682-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15682-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="15682-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="15682-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15682-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15682-112">See also</span></span>
