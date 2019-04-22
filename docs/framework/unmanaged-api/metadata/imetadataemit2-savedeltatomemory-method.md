---
title: Metodo IMetaDataEmit2::SaveDeltaToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa95a737747e9153eb844cddd8e0684585b9108b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081144"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="eb4ad-102">Metodo IMetaDataEmit2::SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="eb4ad-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="eb4ad-103">Salva le modifiche dalla sessione corrente di modifica e continuazione per la memoria.</span><span class="sxs-lookup"><span data-stu-id="eb4ad-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb4ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb4ad-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb4ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb4ad-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="eb4ad-106">[out] L'indirizzo in corrispondenza del quale iniziare a scrivere il delta di metadati.</span><span class="sxs-lookup"><span data-stu-id="eb4ad-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="eb4ad-107">[in] Le dimensioni delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="eb4ad-107">[in] The size of the changes.</span></span> <span data-ttu-id="eb4ad-108">Uso [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) per determinare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="eb4ad-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb4ad-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb4ad-109">Requirements</span></span>  
 <span data-ttu-id="eb4ad-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb4ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb4ad-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eb4ad-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb4ad-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="eb4ad-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb4ad-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb4ad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4ad-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb4ad-114">See also</span></span>

- [<span data-ttu-id="eb4ad-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="eb4ad-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="eb4ad-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="eb4ad-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
