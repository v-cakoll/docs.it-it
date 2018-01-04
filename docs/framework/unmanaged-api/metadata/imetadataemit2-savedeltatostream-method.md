---
title: Metodo IMetaDataEmit2::SaveDeltaToStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDeltaToStream
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bcfd90da200e04e5834b21ea84a3a84acc5b732d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="cd425-102">Metodo IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="cd425-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="cd425-103">Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="cd425-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd425-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd425-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd425-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd425-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="cd425-106">[in] Un puntatore a interfaccia per il flusso scrivibile nel quale salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cd425-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="cd425-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="cd425-107">[in] Reserved.</span></span> <span data-ttu-id="cd425-108">Questo valore deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="cd425-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd425-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd425-109">Requirements</span></span>  
 <span data-ttu-id="cd425-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd425-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd425-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cd425-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd425-112">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd425-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd425-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd425-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd425-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd425-114">See Also</span></span>  
 [<span data-ttu-id="cd425-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cd425-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="cd425-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cd425-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
