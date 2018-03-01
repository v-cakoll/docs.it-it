---
title: Metodo ICLRMetadataLocator::GetMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8758a96464d1465d92fb17314f1e36ab8d9169c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="76625-102">Metodo ICLRMetadataLocator::GetMetadata</span><span class="sxs-lookup"><span data-stu-id="76625-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="76625-103">Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per recuperare i metadati di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="76625-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76625-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76625-104">Syntax</span></span>  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76625-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76625-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="76625-106">[in] Stringa che specifica il percorso del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="76625-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="76625-107">[in] Il timestamp del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="76625-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="76625-108">[in] Le dimensioni del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="76625-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="76625-109">[in] Identificatore univoco globale dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="76625-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="76625-110">[in] L'indirizzo virtuale relativo (RVA) dei metadati.</span><span class="sxs-lookup"><span data-stu-id="76625-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="76625-111">L'indirizzo è relativo all'indirizzo di base di immagine.</span><span class="sxs-lookup"><span data-stu-id="76625-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="76625-112">[in] Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="76625-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="76625-113">[in] Le dimensioni del buffer in cui inserire i metadati.</span><span class="sxs-lookup"><span data-stu-id="76625-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="76625-114">[out] Buffer in cui inserire i metadati.</span><span class="sxs-lookup"><span data-stu-id="76625-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="76625-115">[out] Le dimensioni dei metadati che viene restituito.</span><span class="sxs-lookup"><span data-stu-id="76625-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76625-116">Note</span><span class="sxs-lookup"><span data-stu-id="76625-116">Remarks</span></span>  
 <span data-ttu-id="76625-117">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="76625-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76625-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76625-118">Requirements</span></span>  
 <span data-ttu-id="76625-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76625-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76625-120">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="76625-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="76625-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76625-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76625-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76625-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76625-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76625-123">See Also</span></span>  
 [<span data-ttu-id="76625-124">Interfaccia ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="76625-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
