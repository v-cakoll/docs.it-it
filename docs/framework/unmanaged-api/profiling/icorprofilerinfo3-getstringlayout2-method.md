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
ms.openlocfilehash: f3727343755d7014202f844be28414d31ce55bc1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862256"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="fe7f0-102">Metodo ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="fe7f0-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="fe7f0-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="fe7f0-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="fe7f0-104">Questo metodo sostituisce il metodo [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fe7f0-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe7f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe7f0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe7f0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe7f0-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="fe7f0-107">out Puntatore all'offset della posizione, relativo al puntatore `ObjectID`, in cui è archiviata la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="fe7f0-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="fe7f0-108">La lunghezza viene archiviata come `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="fe7f0-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="fe7f0-109">out Puntatore all'offset del buffer, relativo al puntatore `ObjectID` che archivia la stringa di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="fe7f0-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe7f0-110">Note</span><span class="sxs-lookup"><span data-stu-id="fe7f0-110">Remarks</span></span>  
 <span data-ttu-id="fe7f0-111">Le stringhe possono essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="fe7f0-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe7f0-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fe7f0-112">Requirements</span></span>  
 <span data-ttu-id="fe7f0-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe7f0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe7f0-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe7f0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fe7f0-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe7f0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe7f0-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe7f0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7f0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe7f0-117">See also</span></span>

- [<span data-ttu-id="fe7f0-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="fe7f0-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fe7f0-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="fe7f0-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
