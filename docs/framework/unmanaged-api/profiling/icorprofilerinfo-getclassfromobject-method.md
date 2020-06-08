---
title: Metodo ICorProfilerInfo::GetClassFromObject
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: 613267549329d2f48dcd18ae341e47538e414ac0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498531"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="1a217-102">Metodo ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="1a217-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="1a217-103">Ottiene l' `ClassID` oggetto di un oggetto, dato il relativo oggetto `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="1a217-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a217-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a217-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a217-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a217-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="1a217-106">in ID dell'oggetto per il quale ottenere `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="1a217-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="1a217-107">out Puntatore all'oggetto restituito `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="1a217-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a217-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1a217-108">Remarks</span></span>  
 <span data-ttu-id="1a217-109">Un valore null `pClassId` indica che `objectId` ha un tipo che sta scaricando.</span><span class="sxs-lookup"><span data-stu-id="1a217-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a217-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a217-110">Requirements</span></span>  
 <span data-ttu-id="1a217-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a217-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a217-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a217-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a217-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a217-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a217-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a217-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a217-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a217-115">See also</span></span>

- [<span data-ttu-id="1a217-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1a217-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
