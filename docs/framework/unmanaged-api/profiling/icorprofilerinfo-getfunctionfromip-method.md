---
title: Metodo ICorProfilerInfo::GetFunctionFromIP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionFromIP
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 144d80bb0e4111e319427d6a265d199b04b7f863
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="27355-102">Metodo ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="27355-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="27355-103">Esegue il mapping di un puntatore all'istruzione di codice gestito a un `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="27355-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27355-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27355-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27355-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="27355-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="27355-106">[in] Puntatore all'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="27355-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="27355-107">[out] L'ID restituito di funzione.</span><span class="sxs-lookup"><span data-stu-id="27355-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27355-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27355-108">Requirements</span></span>  
 <span data-ttu-id="27355-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27355-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27355-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27355-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27355-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27355-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27355-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27355-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27355-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27355-113">See Also</span></span>  
 [<span data-ttu-id="27355-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="27355-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
