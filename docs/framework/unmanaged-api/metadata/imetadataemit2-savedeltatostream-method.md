---
title: Metodo IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dcb94323c9950b8e1fe56ca3dae5f41a9c801907
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472122"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="d2b42-102">Metodo IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="d2b42-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="d2b42-103">Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="d2b42-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2b42-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2b42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2b42-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="d2b42-106">[in] Un puntatore a interfaccia nel flusso scrivibile nel quale salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d2b42-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="d2b42-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="d2b42-107">[in] Reserved.</span></span> <span data-ttu-id="d2b42-108">Questo valore deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="d2b42-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2b42-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2b42-109">Requirements</span></span>  
 <span data-ttu-id="d2b42-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2b42-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b42-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d2b42-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2b42-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d2b42-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2b42-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b42-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b42-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b42-114">See also</span></span>
- [<span data-ttu-id="d2b42-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d2b42-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d2b42-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d2b42-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
