---
title: Metodo ICorProfilerInfo::GetModuleMetaData
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ad52460bcd6eb320e970cd0ce2078f2e93df353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="a190d-102">Metodo ICorProfilerInfo::GetModuleMetaData</span><span class="sxs-lookup"><span data-stu-id="a190d-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="a190d-103">Ottiene un'istanza di interfaccia di metadati che esegue il mapping per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="a190d-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a190d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a190d-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a190d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a190d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a190d-106">[in] L'ID del modulo a cui verrà eseguito il mapping l'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a190d-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a190d-107">[in] Il valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione che specifica la modalità di apertura dei file manifesti.</span><span class="sxs-lookup"><span data-stu-id="a190d-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="a190d-108">Solo il `ofRead`, `ofWrite` e `ofNoTransform` bit sono validi.</span><span class="sxs-lookup"><span data-stu-id="a190d-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="a190d-109">[in] Il riferimento all'ID (GUID) dell'interfaccia di metadati la cui istanza verrà recuperato.</span><span class="sxs-lookup"><span data-stu-id="a190d-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="a190d-110">Vedere [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) per un elenco delle interfacce.</span><span class="sxs-lookup"><span data-stu-id="a190d-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="a190d-111">[out] Un puntatore all'indirizzo dell'istanza di interfaccia di metadati.</span><span class="sxs-lookup"><span data-stu-id="a190d-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a190d-112">Note</span><span class="sxs-lookup"><span data-stu-id="a190d-112">Remarks</span></span>  
 <span data-ttu-id="a190d-113">È possibile chiedere che i metadati essere aperto in modalità lettura/scrittura, ma il risultato sarà rallenterà l'esecuzione del programma, perché le modifiche apportate per i metadati non possono essere ottimizzato come avveniva dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="a190d-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="a190d-114">Alcuni moduli (ad esempio, i moduli delle risorse) non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="a190d-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="a190d-115">In questi casi, `GetModuleMetaData` restituirà un valore HRESULT di S_FALSE e un valore null in *`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="a190d-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a190d-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a190d-116">Requirements</span></span>  
 <span data-ttu-id="a190d-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a190d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a190d-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a190d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a190d-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a190d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a190d-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a190d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a190d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a190d-121">See Also</span></span>  
 [<span data-ttu-id="a190d-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a190d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
