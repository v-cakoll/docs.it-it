---
title: Metodo ICorProfilerModuleEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
ms.openlocfilehash: 604ecb2122cce6e24f0e5168fa286a523d8bb4f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495073"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="6811e-102">Metodo ICorProfilerModuleEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="6811e-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="6811e-103">Ottiene il numero di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6811e-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6811e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6811e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6811e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6811e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6811e-106">out Numero di moduli di runtime nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="6811e-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6811e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6811e-107">Requirements</span></span>  
 <span data-ttu-id="6811e-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6811e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6811e-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6811e-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6811e-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6811e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6811e-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6811e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6811e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6811e-112">See also</span></span>

- [<span data-ttu-id="6811e-113">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="6811e-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="6811e-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="6811e-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
