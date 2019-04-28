---
title: Metodo ICorProfilerObjectEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8466de39f2f2769fec332290c187ecba396d7d56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597413"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="86a97-102">Metodo ICorProfilerObjectEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="86a97-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="86a97-103">Ottiene il numero totale di oggetti bloccati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="86a97-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86a97-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86a97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86a97-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="86a97-106">[out] Puntatore al numero di oggetti bloccati nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="86a97-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="86a97-107">Questo metodo restituirà sempre uguale a zero in .NET Framework versione 3.5 Service Pack 1 (SP1) e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="86a97-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86a97-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86a97-108">Requirements</span></span>  
 <span data-ttu-id="86a97-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86a97-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86a97-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86a97-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86a97-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86a97-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86a97-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86a97-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a97-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86a97-113">See also</span></span>

- [<span data-ttu-id="86a97-114">Interfaccia ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="86a97-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
