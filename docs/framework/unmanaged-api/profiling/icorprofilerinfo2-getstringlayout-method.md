---
title: Metodo ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868616"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="29294-102">Metodo ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="29294-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="29294-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="29294-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="29294-104">Questo metodo è deprecato nel .NET Framework 4 e viene sostituito dal metodo [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="29294-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29294-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29294-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29294-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="29294-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="29294-107">out Puntatore all'offset della posizione, relativo al puntatore `ObjectID`, che archivia la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="29294-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="29294-108">La lunghezza viene archiviata come `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="29294-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29294-109">Questo parametro restituisce la lunghezza della stringa stessa, non la lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="29294-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="29294-110">La lunghezza del buffer non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="29294-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="29294-111">out Puntatore all'offset della posizione, relativo al puntatore `ObjectID`, in cui è archiviata la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="29294-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="29294-112">La lunghezza viene archiviata come `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="29294-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="29294-113">out Puntatore all'offset del buffer, relativo al puntatore `ObjectID`, che archivia la stringa di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="29294-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29294-114">Note</span><span class="sxs-lookup"><span data-stu-id="29294-114">Remarks</span></span>  
 <span data-ttu-id="29294-115">Il metodo `GetStringLayout` ottiene gli offset, relativi al puntatore `ObjectID`, delle posizioni in cui sono archiviati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29294-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="29294-116">Lunghezza del buffer della stringa.</span><span class="sxs-lookup"><span data-stu-id="29294-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="29294-117">Lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="29294-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="29294-118">Buffer contenente la stringa effettiva di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="29294-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="29294-119">Le stringhe possono essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="29294-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29294-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="29294-120">Requirements</span></span>  
 <span data-ttu-id="29294-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29294-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29294-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29294-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29294-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29294-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29294-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29294-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29294-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29294-125">See also</span></span>

- [<span data-ttu-id="29294-126">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="29294-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="29294-127">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="29294-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
