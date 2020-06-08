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
ms.openlocfilehash: 1cc05f4c10f4a5b042ff14c05f3c85a7b5935184
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497894"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="eaea7-102">Metodo ICorProfilerInfo::GetTokenAndMetadataFromFunction</span><span class="sxs-lookup"><span data-stu-id="eaea7-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="eaea7-103">Ottiene il token di metadati e un'istanza dell'interfaccia di metadati che possono essere utilizzati per il token per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="eaea7-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaea7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eaea7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaea7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eaea7-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="eaea7-106">in ID della funzione per la quale ottenere il token di metadati e l'interfaccia dei metadati.</span><span class="sxs-lookup"><span data-stu-id="eaea7-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="eaea7-107">in ID di riferimento dell'interfaccia dei metadati per cui ottenere l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="eaea7-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="eaea7-108">out Puntatore all'indirizzo dell'istanza dell'interfaccia dei metadati che può essere utilizzato per il token per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="eaea7-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="eaea7-109">out Puntatore al token di metadati per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="eaea7-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaea7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eaea7-110">Requirements</span></span>  
 <span data-ttu-id="eaea7-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaea7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaea7-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eaea7-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eaea7-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaea7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaea7-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaea7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaea7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaea7-115">See also</span></span>

- [<span data-ttu-id="eaea7-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="eaea7-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
