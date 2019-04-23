---
title: Metodo ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89a2424548bb577e3580d6eaa72f61e5cf9ccc7d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111215"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="0ffab-102">Metodo ICorProfilerInfo::GetModuleMetaData</span><span class="sxs-lookup"><span data-stu-id="0ffab-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="0ffab-103">Ottiene un'istanza di interfaccia di metadati che esegue il mapping per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="0ffab-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ffab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ffab-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ffab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ffab-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0ffab-106">[in] L'ID del modulo a cui verrà mappato l'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0ffab-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="0ffab-107">[in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione che specifica la modalità di apertura dei file manifesto.</span><span class="sxs-lookup"><span data-stu-id="0ffab-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="0ffab-108">Solo le `ofRead`, `ofWrite` e `ofNoTransform` bits sono validi.</span><span class="sxs-lookup"><span data-stu-id="0ffab-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="0ffab-109">[in] Il riferimento all'ID (GUID) dell'interfaccia di metadati la cui istanza verrà recuperato.</span><span class="sxs-lookup"><span data-stu-id="0ffab-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="0ffab-110">Visualizzare [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) per un elenco delle interfacce.</span><span class="sxs-lookup"><span data-stu-id="0ffab-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="0ffab-111">[out] Un puntatore all'indirizzo dell'istanza di interfaccia di metadati.</span><span class="sxs-lookup"><span data-stu-id="0ffab-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ffab-112">Note</span><span class="sxs-lookup"><span data-stu-id="0ffab-112">Remarks</span></span>  
 <span data-ttu-id="0ffab-113">È possibile richiedere i metadati da aprire in modalità lettura/scrittura, ma ciò comporterà rallenterà l'esecuzione del programma, perché le modifiche apportate per i metadati non possono essere ottimizzato come avveniva dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="0ffab-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="0ffab-114">Alcuni moduli (ad esempio, i moduli delle risorse) non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="0ffab-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="0ffab-115">In questi casi `GetModuleMetaData` restituirà un valore HRESULT di S_FALSE e un valore null in \*`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="0ffab-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ffab-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ffab-116">Requirements</span></span>  
 <span data-ttu-id="0ffab-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ffab-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ffab-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ffab-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ffab-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ffab-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ffab-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ffab-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffab-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ffab-121">See also</span></span>

- [<span data-ttu-id="0ffab-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0ffab-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
