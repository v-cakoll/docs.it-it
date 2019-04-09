---
title: Metodo ICorProfilerInfo::GetTokenAndMetadataFromFunction
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e7f2e8247d3ba822cc09a98f985926e6b5400c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206889"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="e5714-102">Metodo ICorProfilerInfo::GetTokenAndMetadataFromFunction</span><span class="sxs-lookup"><span data-stu-id="e5714-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="e5714-103">Ottiene il token di metadati e un'istanza di interfaccia di metadati che può essere utilizzata a fronte del token per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="e5714-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5714-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5714-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5714-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5714-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e5714-106">[in] L'ID della funzione per cui ottenere il token di metadati e l'interfaccia di metadati.</span><span class="sxs-lookup"><span data-stu-id="e5714-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="e5714-107">[in] L'ID di riferimento dell'interfaccia di metadati per ottenere l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="e5714-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="e5714-108">[out] Un puntatore all'indirizzo dell'istanza dell'interfaccia di metadati che può essere utilizzato a fronte del token per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="e5714-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="e5714-109">[out] Puntatore al token di metadati per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="e5714-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5714-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5714-110">Requirements</span></span>  
 <span data-ttu-id="e5714-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5714-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5714-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5714-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5714-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5714-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e5714-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e5714-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e5714-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5714-115">See also</span></span>

- [<span data-ttu-id="e5714-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e5714-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
