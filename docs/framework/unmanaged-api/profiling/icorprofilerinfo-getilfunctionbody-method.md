---
title: Metodo ICorProfilerInfo::GetILFunctionBody
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2960bc0cfc39adb9b7cbca236d495baf630a173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991848"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="33430-102">Metodo ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="33430-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="33430-103">Ottiene un puntatore al corpo di un metodo in codice Microsoft intermediate language (MSIL), a partire dalla relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="33430-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33430-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33430-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33430-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="33430-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="33430-106">[in] L'ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="33430-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="33430-107">[in] Il token di metadati per il metodo.</span><span class="sxs-lookup"><span data-stu-id="33430-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="33430-108">[out] Un puntatore all'intestazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="33430-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="33430-109">[out] Valore intero che specifica la dimensione del metodo.</span><span class="sxs-lookup"><span data-stu-id="33430-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33430-110">Note</span><span class="sxs-lookup"><span data-stu-id="33430-110">Remarks</span></span>  
 <span data-ttu-id="33430-111">L'ambito di un metodo è limitato dal modulo in cui si trovino.</span><span class="sxs-lookup"><span data-stu-id="33430-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="33430-112">Poiché il `GetILFunctionBody` metodo è progettato per fornire l'accesso dello strumento per il codice MSIL prima che sia stato caricato da common language runtime (CLR), Usa il token di metadati del metodo per trovare l'istanza desiderata.</span><span class="sxs-lookup"><span data-stu-id="33430-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="33430-113">`GetILFunctionBody` può restituire un valore HRESULT CORPROF_E_FUNCTION_NOT_IL se il `methodId` punta a un metodo senza codice MSIL (ad esempio un metodo astratto, o un platform invoke (PInvoke) metodo).</span><span class="sxs-lookup"><span data-stu-id="33430-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33430-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33430-114">Requirements</span></span>  
 <span data-ttu-id="33430-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33430-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33430-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33430-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33430-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33430-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33430-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33430-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33430-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33430-119">See also</span></span>

- [<span data-ttu-id="33430-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="33430-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
