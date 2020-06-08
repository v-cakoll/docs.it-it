---
title: Metodo ICorProfilerThreadEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: 4bc2ea083d5278afc9278d388f57b048f7682ca6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494397"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="84a95-102">Metodo ICorProfilerThreadEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="84a95-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="84a95-103">Ottiene il numero di thread usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="84a95-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84a95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84a95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84a95-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="84a95-106">out Numero di thread utilizzati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="84a95-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a95-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84a95-107">Requirements</span></span>  
 <span data-ttu-id="84a95-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a95-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a95-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84a95-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84a95-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84a95-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84a95-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a95-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a95-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84a95-112">See also</span></span>

- [<span data-ttu-id="84a95-113">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="84a95-113">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="84a95-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="84a95-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
