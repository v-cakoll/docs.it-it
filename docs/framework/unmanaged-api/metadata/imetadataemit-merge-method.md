---
title: Metodo IMetaDataEmit::Merge
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175707"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="f2e58-102">Metodo IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="f2e58-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="f2e58-103">Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.</span><span class="sxs-lookup"><span data-stu-id="f2e58-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2e58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2e58-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2e58-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2e58-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="f2e58-106">[in] Puntatore a un oggetto [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che identifica l'ambito importato da unire.</span><span class="sxs-lookup"><span data-stu-id="f2e58-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="f2e58-107">[in] Puntatore a un oggetto [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) che specifica il nuovo mapping del token.</span><span class="sxs-lookup"><span data-stu-id="f2e58-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="f2e58-108">[in] Puntatore a un oggetto [IUnknown](/cpp/atl/iunknown) che specifica gli errori.</span><span class="sxs-lookup"><span data-stu-id="f2e58-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2e58-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f2e58-109">Remarks</span></span>  
 <span data-ttu-id="f2e58-110">Chiamare [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) per attivare la fusione dei metadati in un singolo ambito.</span><span class="sxs-lookup"><span data-stu-id="f2e58-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2e58-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2e58-111">Requirements</span></span>  
 <span data-ttu-id="f2e58-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2e58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2e58-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2e58-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2e58-114">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2e58-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2e58-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2e58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e58-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2e58-116">See also</span></span>

- [<span data-ttu-id="f2e58-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f2e58-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f2e58-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f2e58-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
