---
title: Metodo ICorProfilerInfo4::GetObjectSize2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: 441f7743ba01884592393ce9382348fbecaeaa9d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861879"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="9d217-102">Metodo ICorProfilerInfo4::GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="9d217-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="9d217-103">Restituisce la dimensione di un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="9d217-103">Returns the size of a specified object.</span></span> <span data-ttu-id="9d217-104">Sostituisce il metodo [ICorProfilerInfo:: GetObjectSize](icorprofilerinfo-getobjectsize-method.md) segnalando dimensioni di oggetti maggiori di quelli che possono essere espressi in una `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="9d217-104">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d217-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d217-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d217-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d217-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="9d217-107">in ID dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9d217-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="9d217-108">out Puntatore alla dimensione dell'oggetto, in byte.</span><span class="sxs-lookup"><span data-stu-id="9d217-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d217-109">Note</span><span class="sxs-lookup"><span data-stu-id="9d217-109">Remarks</span></span>  
 <span data-ttu-id="9d217-110">Oggetti diversi degli stessi tipi spesso hanno le stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9d217-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="9d217-111">Tuttavia, alcuni tipi, ad esempio matrici o stringhe, possono avere dimensioni diverse per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="9d217-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d217-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9d217-112">Requirements</span></span>  
 <span data-ttu-id="9d217-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d217-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d217-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d217-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d217-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d217-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d217-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d217-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d217-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d217-117">See also</span></span>

- [<span data-ttu-id="9d217-118">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="9d217-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
