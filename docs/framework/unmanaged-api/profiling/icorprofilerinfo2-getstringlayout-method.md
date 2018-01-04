---
title: Metodo ICorProfilerInfo2::GetStringLayout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ad91829fab31b47a1dd51bb6cc9118c2ebe4c3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="65231-102">Metodo ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="65231-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="65231-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="65231-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="65231-104">Questo metodo è deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]ed è stato sostituito il [ICorProfilerInfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="65231-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65231-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65231-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65231-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="65231-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="65231-107">[out] Un puntatore all'offset della posizione relativa al `ObjectID` puntatore, che archivia la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="65231-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="65231-108">La lunghezza viene archiviata come un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="65231-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65231-109">Questo parametro restituisce la lunghezza della stringa stessa, non la lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="65231-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="65231-110">La lunghezza del buffer non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="65231-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="65231-111">[out] Un puntatore all'offset della posizione relativa al `ObjectID` puntatore, che archivia la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="65231-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="65231-112">La lunghezza viene archiviata come un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="65231-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="65231-113">[out] Un puntatore all'offset del buffer relativo al `ObjectID` puntatore, che archivia la stringa di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="65231-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65231-114">Note</span><span class="sxs-lookup"><span data-stu-id="65231-114">Remarks</span></span>  
 <span data-ttu-id="65231-115">Il `GetStringLayout` metodo ottiene gli offset, relativo al `ObjectID` puntatore, delle posizioni in cui sono archiviate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="65231-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="65231-116">La lunghezza del buffer della stringa.</span><span class="sxs-lookup"><span data-stu-id="65231-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="65231-117">La lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="65231-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="65231-118">Buffer che contiene la stringa effettiva di caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="65231-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="65231-119">Le stringhe possono essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="65231-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65231-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65231-120">Requirements</span></span>  
 <span data-ttu-id="65231-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65231-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65231-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65231-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65231-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65231-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65231-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65231-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65231-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65231-125">See Also</span></span>  
 [<span data-ttu-id="65231-126">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="65231-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="65231-127">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="65231-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
