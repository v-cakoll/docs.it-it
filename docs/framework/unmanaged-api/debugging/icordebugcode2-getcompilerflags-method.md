---
title: Metodo ICorDebugCode2::GetCompilerFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2.GetCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42a4b8e54bd1ca7706be7e23653681430fb41a8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="e78d8-102">Metodo ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="e78d8-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="e78d8-103">Ottiene i flag che specificano le condizioni in cui questo oggetto di codice è stato uno just-in-time (JIT) compilata o generato utilizzando il generatore di immagini native (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="e78d8-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e78d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e78d8-104">Syntax</span></span>  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e78d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e78d8-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="e78d8-106">[out] Un puntatore a un valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che specifica il comportamento del compilatore JIT o il generatore di immagini native.</span><span class="sxs-lookup"><span data-stu-id="e78d8-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e78d8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e78d8-107">Requirements</span></span>  
 <span data-ttu-id="e78d8-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e78d8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e78d8-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e78d8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e78d8-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e78d8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e78d8-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e78d8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78d8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e78d8-112">See Also</span></span>  
 
