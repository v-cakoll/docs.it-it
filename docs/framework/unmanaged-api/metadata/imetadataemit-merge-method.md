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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 899f2ca5ef1b987687f5c065ad3e1965e142d103
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216106"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="3b78c-102">Metodo IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="3b78c-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="3b78c-103">Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.</span><span class="sxs-lookup"><span data-stu-id="3b78c-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b78c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b78c-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b78c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b78c-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="3b78c-106">[in] Un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) oggetto che identifica l'ambito importato da unire.</span><span class="sxs-lookup"><span data-stu-id="3b78c-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="3b78c-107">[in] Un puntatore a un [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) oggetto che specifica il nuovo mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="3b78c-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="3b78c-108">[in] Un puntatore a un [IUnknown](/cpp/atl/iunknown) oggetto che specifica gli errori.</span><span class="sxs-lookup"><span data-stu-id="3b78c-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b78c-109">Note</span><span class="sxs-lookup"><span data-stu-id="3b78c-109">Remarks</span></span>  
 <span data-ttu-id="3b78c-110">Chiamare [MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) per attivare l'unione dei metadati in un singolo ambito.</span><span class="sxs-lookup"><span data-stu-id="3b78c-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b78c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b78c-111">Requirements</span></span>  
 <span data-ttu-id="3b78c-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b78c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b78c-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3b78c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b78c-114">**Libreria:** usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3b78c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b78c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b78c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b78c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b78c-116">See Also</span></span>  
 [<span data-ttu-id="3b78c-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3b78c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="3b78c-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3b78c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
