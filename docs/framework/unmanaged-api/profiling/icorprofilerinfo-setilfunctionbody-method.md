---
title: Metodo ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 462fc7222243f8cad4e1d03d1717eedace549836
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502938"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="6625e-102">Metodo ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="6625e-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="6625e-103">Sostituisce il corpo della funzione specificata nel modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="6625e-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6625e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6625e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6625e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6625e-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="6625e-106">in ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="6625e-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="6625e-107">in Token della funzione per cui sostituire il corpo.</span><span class="sxs-lookup"><span data-stu-id="6625e-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="6625e-108">in Nuova intestazione per la funzione.</span><span class="sxs-lookup"><span data-stu-id="6625e-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6625e-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6625e-109">Remarks</span></span>  
 <span data-ttu-id="6625e-110">Il `SetILFunctionBody` metodo sostituisce l'indirizzo virtuale relativo della funzione nei metadati in modo che punti al nuovo corpo della funzione e modifichi tutte le strutture di dati interne in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="6625e-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="6625e-111">Il `SetILFunctionBody` metodo può essere chiamato solo sulle funzioni che non sono mai state compilate da un compilatore JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="6625e-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="6625e-112">Usare il metodo [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) per allocare spazio al nuovo metodo per assicurarsi che il buffer sia compatibile.</span><span class="sxs-lookup"><span data-stu-id="6625e-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6625e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6625e-113">Requirements</span></span>  
 <span data-ttu-id="6625e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6625e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6625e-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6625e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6625e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6625e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6625e-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6625e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6625e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6625e-118">See also</span></span>

- [<span data-ttu-id="6625e-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6625e-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
