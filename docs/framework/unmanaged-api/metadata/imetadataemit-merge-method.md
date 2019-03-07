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
ms.openlocfilehash: 47b59c7393d9d4e9cbdeaa1a2efd9965f969f985
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497795"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="7e639-102">Metodo IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="7e639-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="7e639-103">Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.</span><span class="sxs-lookup"><span data-stu-id="7e639-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e639-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e639-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e639-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e639-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="7e639-106">[in] Un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) oggetto che identifica l'ambito importato da unire.</span><span class="sxs-lookup"><span data-stu-id="7e639-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="7e639-107">[in] Un puntatore a un [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) oggetto che specifica il nuovo mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="7e639-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="7e639-108">[in] Un puntatore a un [IUnknown](/cpp/atl/iunknown) oggetto che specifica gli errori.</span><span class="sxs-lookup"><span data-stu-id="7e639-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e639-109">Note</span><span class="sxs-lookup"><span data-stu-id="7e639-109">Remarks</span></span>  
 <span data-ttu-id="7e639-110">Chiamare [MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) per attivare l'unione dei metadati in un singolo ambito.</span><span class="sxs-lookup"><span data-stu-id="7e639-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e639-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e639-111">Requirements</span></span>  
 <span data-ttu-id="7e639-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e639-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e639-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7e639-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e639-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7e639-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e639-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e639-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e639-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e639-116">See also</span></span>
- [<span data-ttu-id="7e639-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7e639-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7e639-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7e639-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
