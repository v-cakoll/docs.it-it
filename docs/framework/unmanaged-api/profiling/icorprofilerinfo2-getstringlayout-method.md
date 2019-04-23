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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc94c63edb602d87a7c08a9051eb2ef760834477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200974"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="39a1a-102">Metodo ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="39a1a-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="39a1a-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="39a1a-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="39a1a-104">Questo metodo è deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]ed è stato sostituito il [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="39a1a-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a1a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39a1a-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39a1a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="39a1a-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="39a1a-107">[out] Un puntatore all'offset della posizione relativa per il `ObjectID` puntatore, che archivia la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="39a1a-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="39a1a-108">La lunghezza viene archiviata come un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="39a1a-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39a1a-109">Questo parametro restituisce la lunghezza della stringa, non la lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="39a1a-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="39a1a-110">La lunghezza del buffer non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="39a1a-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="39a1a-111">[out] Un puntatore all'offset della posizione relativa per il `ObjectID` puntatore, che archivia la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="39a1a-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="39a1a-112">La lunghezza viene archiviata come un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="39a1a-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="39a1a-113">[out] L'offset del buffer relativo a un puntatore di `ObjectID` puntatore, che archivia la stringa di caratteri "wide".</span><span class="sxs-lookup"><span data-stu-id="39a1a-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39a1a-114">Note</span><span class="sxs-lookup"><span data-stu-id="39a1a-114">Remarks</span></span>  
 <span data-ttu-id="39a1a-115">Il `GetStringLayout` metodo ottiene gli offset rispetto al `ObjectID` puntatore, delle posizioni in cui sono archiviati i seguenti:</span><span class="sxs-lookup"><span data-stu-id="39a1a-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="39a1a-116">Lunghezza del buffer della stringa.</span><span class="sxs-lookup"><span data-stu-id="39a1a-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="39a1a-117">La lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="39a1a-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="39a1a-118">Buffer che contiene la stringa effettiva di caratteri "wide".</span><span class="sxs-lookup"><span data-stu-id="39a1a-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="39a1a-119">Le stringhe possono essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="39a1a-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a1a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39a1a-120">Requirements</span></span>  
 <span data-ttu-id="39a1a-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a1a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a1a-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39a1a-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39a1a-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39a1a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a1a-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a1a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a1a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39a1a-125">See also</span></span>

- [<span data-ttu-id="39a1a-126">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="39a1a-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="39a1a-127">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="39a1a-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
