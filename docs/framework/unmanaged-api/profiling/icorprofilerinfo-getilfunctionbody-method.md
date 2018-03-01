---
title: Metodo ICorProfilerInfo::GetILFunctionBody
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 035c2a1926d80b4aaea57523b4ecdd3da6873efe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="7a9f9-102">Metodo ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="7a9f9-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="7a9f9-103">Ottiene un puntatore al corpo di un metodo nel codice di Microsoft intermediate language (MSIL), a partire dalla relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a9f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a9f9-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a9f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a9f9-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="7a9f9-106">[in] L'ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="7a9f9-107">[in] Il token di metadati per il metodo.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="7a9f9-108">[out] Un puntatore all'intestazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="7a9f9-109">[out] Valore intero che specifica le dimensioni del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a9f9-110">Note</span><span class="sxs-lookup"><span data-stu-id="7a9f9-110">Remarks</span></span>  
 <span data-ttu-id="7a9f9-111">L'ambito di un metodo è il modulo in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="7a9f9-112">Poiché il `GetILFunctionBody` metodo è progettato per dare un strumento di accesso al codice MSIL prima che sia stato caricato da common language runtime (CLR), Usa il token di metadati del metodo per trovare l'istanza desiderata.</span><span class="sxs-lookup"><span data-stu-id="7a9f9-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="7a9f9-113">`GetILFunctionBody`può restituire un valore HRESULT CORPROF_E_FUNCTION_NOT_IL se il `methodId` punta a un metodo senza codice MSIL (ad esempio un metodo astratto, o un platform invoke (metodo) (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="7a9f9-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a9f9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a9f9-114">Requirements</span></span>  
 <span data-ttu-id="7a9f9-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a9f9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a9f9-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a9f9-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a9f9-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a9f9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a9f9-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a9f9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9f9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a9f9-119">See Also</span></span>  
 [<span data-ttu-id="7a9f9-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7a9f9-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
