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
ms.openlocfilehash: a7ec50c91ce02958d0d44643d4f79da1680532aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450366"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="dc5a8-102">Metodo ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="dc5a8-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="dc5a8-103">Ottiene un puntatore al corpo di un metodo nel codice MSIL (Microsoft Intermediate Language), a partire dalla relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc5a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc5a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc5a8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="dc5a8-106">in ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="dc5a8-107">in Token di metadati per il metodo.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="dc5a8-108">out Puntatore all'intestazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="dc5a8-109">out Integer che specifica le dimensioni del metodo.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc5a8-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dc5a8-110">Remarks</span></span>  
 <span data-ttu-id="dc5a8-111">Un metodo ha come ambito il modulo in cui risiede.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="dc5a8-112">Poiché il metodo `GetILFunctionBody` è progettato per concedere a uno strumento l'accesso al codice MSIL prima che sia stato caricato dal Common Language Runtime (CLR), usa il token di metadati del metodo per trovare l'istanza desiderata.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="dc5a8-113">`GetILFunctionBody` possibile restituire un valore HRESULT CORPROF_E_FUNCTION_NOT_IL se il `methodId` punta a un metodo senza codice MSIL, ad esempio un metodo astratto o un metodo platform invoke (PInvoke).</span><span class="sxs-lookup"><span data-stu-id="dc5a8-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc5a8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc5a8-114">Requirements</span></span>  
 <span data-ttu-id="dc5a8-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc5a8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc5a8-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc5a8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc5a8-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc5a8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc5a8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc5a8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5a8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc5a8-119">See also</span></span>

- [<span data-ttu-id="dc5a8-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="dc5a8-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
