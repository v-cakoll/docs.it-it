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
ms.openlocfilehash: b3e14230888e9bf846879d5728c2b20883fb8d53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438736"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="b6540-102">Metodo ICorProfilerInfo::GetTokenAndMetadataFromFunction</span><span class="sxs-lookup"><span data-stu-id="b6540-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="b6540-103">Ottiene il token di metadati e un'istanza dell'interfaccia di metadati che possono essere utilizzati per il token per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="b6540-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6540-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6540-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6540-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6540-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b6540-106">in ID della funzione per la quale ottenere il token di metadati e l'interfaccia dei metadati.</span><span class="sxs-lookup"><span data-stu-id="b6540-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="b6540-107">in ID di riferimento dell'interfaccia dei metadati per cui ottenere l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="b6540-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="b6540-108">out Puntatore all'indirizzo dell'istanza dell'interfaccia dei metadati che può essere utilizzato per il token per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="b6540-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="b6540-109">out Puntatore al token di metadati per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="b6540-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6540-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6540-110">Requirements</span></span>  
 <span data-ttu-id="b6540-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6540-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6540-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6540-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6540-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6540-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6540-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6540-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6540-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6540-115">See also</span></span>

- [<span data-ttu-id="b6540-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b6540-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
