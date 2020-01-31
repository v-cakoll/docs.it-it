---
title: Metodo ICorProfilerInfo2::GetStaticFieldInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: d30d0bc262d76cf8980f90d8384173d89baf92d5
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862685"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="16c11-102">Metodo ICorProfilerInfo2::GetStaticFieldInfo</span><span class="sxs-lookup"><span data-stu-id="16c11-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="16c11-103">Ottiene un valore che indica il tipo di statico che si applica al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="16c11-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16c11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16c11-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16c11-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="16c11-106">in ID della classe in cui è definito il campo statico.</span><span class="sxs-lookup"><span data-stu-id="16c11-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="16c11-107">in Token di metadati per il campo statico.</span><span class="sxs-lookup"><span data-stu-id="16c11-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="16c11-108">out Puntatore a un valore dell'enumerazione [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) che indica se il campo specificato è statico e, in tal caso, il tipo di statico applicato al campo.</span><span class="sxs-lookup"><span data-stu-id="16c11-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16c11-109">Note</span><span class="sxs-lookup"><span data-stu-id="16c11-109">Remarks</span></span>  
 <span data-ttu-id="16c11-110">Queste informazioni possono essere usate per determinare la funzione da chiamare per ottenere l'indirizzo del campo statico.</span><span class="sxs-lookup"><span data-stu-id="16c11-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="16c11-111">Il codice del profiler dovrebbe ancora verificare i metadati per un campo statico per assicurarsi che disponga effettivamente di un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="16c11-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="16c11-112">I valori letterali statici, ovvero le costanti, esistono solo nei metadati e non hanno un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="16c11-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c11-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="16c11-113">Requirements</span></span>  
 <span data-ttu-id="16c11-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16c11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16c11-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16c11-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16c11-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16c11-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16c11-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16c11-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c11-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16c11-118">See also</span></span>

- [<span data-ttu-id="16c11-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="16c11-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="16c11-120">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="16c11-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
