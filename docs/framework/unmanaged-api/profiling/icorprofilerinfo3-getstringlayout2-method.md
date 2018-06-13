---
title: Metodo ICorProfilerInfo3::GetStringLayout2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57a21a3e4c1324e15a8418dacb8cfe7c5163f334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454410"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="f9819-102">Metodo ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="f9819-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="f9819-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="f9819-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="f9819-104">Questo metodo sostituisce il [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="f9819-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9819-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9819-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9819-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9819-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="f9819-107">[out] Un puntatore all'offset della posizione relativa al `ObjectID` puntatore, che archivia la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="f9819-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="f9819-108">La lunghezza viene archiviata come un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="f9819-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f9819-109">[out] Un puntatore all'offset del buffer relativo al `ObjectID` puntatore, che archivia la stringa di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="f9819-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9819-110">Note</span><span class="sxs-lookup"><span data-stu-id="f9819-110">Remarks</span></span>  
 <span data-ttu-id="f9819-111">Le stringhe possono o non possono essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="f9819-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9819-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9819-112">Requirements</span></span>  
 <span data-ttu-id="f9819-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9819-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9819-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9819-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9819-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f9819-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9819-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9819-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9819-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9819-117">See Also</span></span>  
 [<span data-ttu-id="f9819-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="f9819-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="f9819-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f9819-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
