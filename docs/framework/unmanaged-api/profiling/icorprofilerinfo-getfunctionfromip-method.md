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
ms.openlocfilehash: 23fb9c58f2eac904b63294434654f3caf1ba9f41
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107965"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="1c057-102">Metodo ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="1c057-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="1c057-103">Esegue il mapping di un puntatore all'istruzione di codice gestito per una `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="1c057-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c057-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c057-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c057-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c057-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="1c057-106">[in] Il puntatore dell'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1c057-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="1c057-107">[out] L'ID restituito di funzione.</span><span class="sxs-lookup"><span data-stu-id="1c057-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c057-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c057-108">Requirements</span></span>  
 <span data-ttu-id="1c057-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c057-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c057-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c057-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c057-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c057-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1c057-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1c057-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c057-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c057-113">See also</span></span>

- [<span data-ttu-id="1c057-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1c057-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
