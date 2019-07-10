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
ms.openlocfilehash: 8a9f6e63a1f24043ac502d139f735cada599df4f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780673"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="0f756-102">Metodo ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="0f756-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="0f756-103">Esegue il mapping di un puntatore all'istruzione di codice gestito per una `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="0f756-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f756-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f756-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f756-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f756-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="0f756-106">[in] Il puntatore dell'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="0f756-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="0f756-107">[out] L'ID restituito di funzione.</span><span class="sxs-lookup"><span data-stu-id="0f756-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f756-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f756-108">Requirements</span></span>  
 <span data-ttu-id="0f756-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f756-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f756-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f756-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f756-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f756-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f756-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f756-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f756-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f756-113">See also</span></span>

- [<span data-ttu-id="0f756-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0f756-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
