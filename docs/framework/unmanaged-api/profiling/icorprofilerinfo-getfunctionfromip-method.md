---
title: Metodo ICorProfilerInfo::GetFunctionFromIP
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fba01c1dfdea83b2580f45b7dbcef91fb7b73fb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452904"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="5413f-102">Metodo ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="5413f-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="5413f-103">Esegue il mapping di un puntatore all'istruzione di codice gestito a un `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="5413f-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5413f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5413f-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5413f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5413f-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="5413f-106">[in] Puntatore all'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5413f-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="5413f-107">[out] L'ID restituito di funzione.</span><span class="sxs-lookup"><span data-stu-id="5413f-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5413f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5413f-108">Requirements</span></span>  
 <span data-ttu-id="5413f-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5413f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5413f-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5413f-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5413f-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5413f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5413f-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5413f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5413f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5413f-113">See Also</span></span>  
 [<span data-ttu-id="5413f-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5413f-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
