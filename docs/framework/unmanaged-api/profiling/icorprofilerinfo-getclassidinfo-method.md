---
title: Metodo ICorProfilerInfo::GetClassIDInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 4fbee938ae86b338f2beb0b48feeee46f144a4a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498492"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="ef980-102">Metodo ICorProfilerInfo::GetClassIDInfo</span><span class="sxs-lookup"><span data-stu-id="ef980-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="ef980-103">Ottiene il modulo padre e il token di metadati per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="ef980-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef980-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef980-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef980-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef980-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ef980-106">in ID della classe per cui ottenere le informazioni.</span><span class="sxs-lookup"><span data-stu-id="ef980-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="ef980-107">out Puntatore all'ID del modulo padre della classe.</span><span class="sxs-lookup"><span data-stu-id="ef980-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="ef980-108">out Puntatore al token di metadati per la classe.</span><span class="sxs-lookup"><span data-stu-id="ef980-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef980-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef980-109">Remarks</span></span>  
 <span data-ttu-id="ef980-110">Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) per ottenere un'interfaccia di metadati per un determinato modulo.</span><span class="sxs-lookup"><span data-stu-id="ef980-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="ef980-111">Il token di metadati restituito al percorso a cui viene fatto riferimento tramite `pTypeDefToken` può quindi essere usato per accedere ai metadati per la classe.</span><span class="sxs-lookup"><span data-stu-id="ef980-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="ef980-112">Per ottenere altre informazioni per i tipi generici, usare [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="ef980-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef980-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef980-113">Requirements</span></span>  
 <span data-ttu-id="ef980-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef980-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef980-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef980-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef980-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef980-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef980-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef980-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef980-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef980-118">See also</span></span>

- [<span data-ttu-id="ef980-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ef980-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
