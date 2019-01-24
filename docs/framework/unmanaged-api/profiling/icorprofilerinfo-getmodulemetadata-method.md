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
ms.openlocfilehash: 1663a36ab36980af709a861b3fb0666be6fecdfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607475"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="4f0ab-102">Metodo ICorProfilerInfo::GetModuleMetaData</span><span class="sxs-lookup"><span data-stu-id="4f0ab-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="4f0ab-103">Ottiene un'istanza di interfaccia di metadati che esegue il mapping per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f0ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f0ab-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f0ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f0ab-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4f0ab-106">[in] L'ID del modulo a cui verrà mappato l'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="4f0ab-107">[in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione che specifica la modalità di apertura dei file manifesto.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="4f0ab-108">Solo le `ofRead`, `ofWrite` e `ofNoTransform` bits sono validi.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="4f0ab-109">[in] Il riferimento all'ID (GUID) dell'interfaccia di metadati la cui istanza verrà recuperato.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="4f0ab-110">Visualizzare [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) per un elenco delle interfacce.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="4f0ab-111">[out] Un puntatore all'indirizzo dell'istanza di interfaccia di metadati.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f0ab-112">Note</span><span class="sxs-lookup"><span data-stu-id="4f0ab-112">Remarks</span></span>  
 <span data-ttu-id="4f0ab-113">È possibile richiedere i metadati da aprire in modalità lettura/scrittura, ma ciò comporterà rallenterà l'esecuzione del programma, perché le modifiche apportate per i metadati non possono essere ottimizzato come avveniva dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="4f0ab-114">Alcuni moduli (ad esempio, i moduli delle risorse) non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="4f0ab-115">In questi casi `GetModuleMetaData` restituirà un valore HRESULT di S_FALSE e un valore null in \*`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="4f0ab-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f0ab-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f0ab-116">Requirements</span></span>  
 <span data-ttu-id="4f0ab-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f0ab-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f0ab-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f0ab-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f0ab-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f0ab-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f0ab-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0ab-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0ab-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f0ab-121">See also</span></span>
- [<span data-ttu-id="4f0ab-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="4f0ab-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
