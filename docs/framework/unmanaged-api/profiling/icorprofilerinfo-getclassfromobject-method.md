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
ms.openlocfilehash: a5573765486112a83f5ea7cc9258447692f72166
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864068"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="bc6fb-102">Metodo ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="bc6fb-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="bc6fb-103">Ottiene l'`ClassID` di un oggetto, in base al relativo `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc6fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc6fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc6fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bc6fb-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="bc6fb-106">in ID dell'oggetto per il quale ottenere il `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="bc6fb-107">out Puntatore al `ClassID`restituito.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc6fb-108">Note</span><span class="sxs-lookup"><span data-stu-id="bc6fb-108">Remarks</span></span>  
 <span data-ttu-id="bc6fb-109">Un `pClassId` null indica che `objectId` dispone di un tipo che sta scaricando.</span><span class="sxs-lookup"><span data-stu-id="bc6fb-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc6fb-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="bc6fb-110">Requirements</span></span>  
 <span data-ttu-id="bc6fb-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc6fb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc6fb-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc6fb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc6fb-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc6fb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc6fb-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc6fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc6fb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc6fb-115">See also</span></span>

- [<span data-ttu-id="bc6fb-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="bc6fb-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
