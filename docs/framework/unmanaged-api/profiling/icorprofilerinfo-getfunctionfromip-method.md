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
ms.openlocfilehash: 339c5db1610a3cf087085ce19fc663436d9c4ec1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498310"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="03cf3-102">Metodo ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="03cf3-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="03cf3-103">Esegue il mapping di un puntatore all'istruzione di codice gestito a `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="03cf3-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03cf3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03cf3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03cf3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03cf3-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="03cf3-106">\[in] puntatore all'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="03cf3-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="03cf3-107">\[out] ID funzione restituito.</span><span class="sxs-lookup"><span data-stu-id="03cf3-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="03cf3-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03cf3-108">Requirements</span></span>  
 <span data-ttu-id="03cf3-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03cf3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03cf3-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03cf3-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03cf3-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03cf3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03cf3-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03cf3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03cf3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03cf3-113">See also</span></span>

- [<span data-ttu-id="03cf3-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="03cf3-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
