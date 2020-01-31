---
title: Metodo ICLRMetadataLocator::GetMetadata
ms.date: 03/30/2017
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
ms.openlocfilehash: 66b3934d000b4f000c368acb1f57c8fc82a5c453
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793617"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="26257-102">Metodo ICLRMetadataLocator::GetMetadata</span><span class="sxs-lookup"><span data-stu-id="26257-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="26257-103">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare i metadati di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="26257-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26257-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26257-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="26257-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26257-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="26257-106">in Stringa che specifica il percorso del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="26257-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="26257-107">in Timestamp del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="26257-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="26257-108">in Dimensioni del file di immagine.</span><span class="sxs-lookup"><span data-stu-id="26257-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="26257-109">in Identificatore univoco globale dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="26257-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="26257-110">in Indirizzo RVA (relativo Virtual Address) dei metadati.</span><span class="sxs-lookup"><span data-stu-id="26257-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="26257-111">L'indirizzo è relativo all'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="26257-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="26257-112">in Riservato per usi futuri.</span><span class="sxs-lookup"><span data-stu-id="26257-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="26257-113">in Dimensione del buffer in cui inserire i metadati.</span><span class="sxs-lookup"><span data-stu-id="26257-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="26257-114">out Buffer in cui inserire i metadati.</span><span class="sxs-lookup"><span data-stu-id="26257-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="26257-115">out Dimensioni dei metadati restituiti.</span><span class="sxs-lookup"><span data-stu-id="26257-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26257-116">Note</span><span class="sxs-lookup"><span data-stu-id="26257-116">Remarks</span></span>  
 <span data-ttu-id="26257-117">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="26257-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26257-118">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="26257-118">Requirements</span></span>  
 <span data-ttu-id="26257-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26257-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26257-120">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="26257-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="26257-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26257-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26257-122">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26257-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26257-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26257-123">See also</span></span>

- [<span data-ttu-id="26257-124">Interfaccia ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="26257-124">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
