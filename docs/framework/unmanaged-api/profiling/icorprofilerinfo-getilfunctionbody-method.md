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
ms.openlocfilehash: 8160bb5b9ca5e0a4e22a1a831e978eaf125e7605
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870492"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="608ad-102">Metodo ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="608ad-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="608ad-103">Ottiene un puntatore al corpo di un metodo nel codice MSIL (Microsoft Intermediate Language), a partire dalla relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="608ad-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="608ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="608ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="608ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="608ad-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="608ad-106">in ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="608ad-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="608ad-107">in Token di metadati per il metodo.</span><span class="sxs-lookup"><span data-stu-id="608ad-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="608ad-108">out Puntatore all'intestazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="608ad-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="608ad-109">out Integer che specifica le dimensioni del metodo.</span><span class="sxs-lookup"><span data-stu-id="608ad-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="608ad-110">Note</span><span class="sxs-lookup"><span data-stu-id="608ad-110">Remarks</span></span>  
 <span data-ttu-id="608ad-111">Un metodo ha come ambito il modulo in cui risiede.</span><span class="sxs-lookup"><span data-stu-id="608ad-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="608ad-112">Poiché il metodo `GetILFunctionBody` è progettato per concedere a uno strumento l'accesso al codice MSIL prima che sia stato caricato dal Common Language Runtime (CLR), usa il token di metadati del metodo per trovare l'istanza desiderata.</span><span class="sxs-lookup"><span data-stu-id="608ad-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="608ad-113">`GetILFunctionBody` possibile restituire un valore HRESULT CORPROF_E_FUNCTION_NOT_IL se il `methodId` punta a un metodo senza codice MSIL, ad esempio un metodo astratto o un metodo platform invoke (PInvoke).</span><span class="sxs-lookup"><span data-stu-id="608ad-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="608ad-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="608ad-114">Requirements</span></span>  
 <span data-ttu-id="608ad-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="608ad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="608ad-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="608ad-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="608ad-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="608ad-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="608ad-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="608ad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608ad-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="608ad-119">See also</span></span>

- [<span data-ttu-id="608ad-120">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="608ad-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
