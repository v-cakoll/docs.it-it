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
ms.openlocfilehash: 51d5b2f2ee17cc177e3b0ddc7d2e0b82fd70063d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496373"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="2a182-102">Metodo ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="2a182-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="2a182-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="2a182-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="2a182-104">Questo metodo sostituisce il metodo [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2a182-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a182-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a182-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a182-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a182-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="2a182-107">out Puntatore all'offset della posizione, relativo al `ObjectID` puntatore, che archivia la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="2a182-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="2a182-108">La lunghezza viene archiviata come `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="2a182-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="2a182-109">out Puntatore all'offset del buffer, relativo al `ObjectID` puntatore, che archivia la stringa di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="2a182-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a182-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2a182-110">Remarks</span></span>  
 <span data-ttu-id="2a182-111">Le stringhe possono essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="2a182-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a182-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a182-112">Requirements</span></span>  
 <span data-ttu-id="2a182-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a182-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a182-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a182-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a182-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a182-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a182-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a182-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a182-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a182-117">See also</span></span>

- [<span data-ttu-id="2a182-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="2a182-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="2a182-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="2a182-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
