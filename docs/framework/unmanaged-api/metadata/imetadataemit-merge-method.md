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
ms.openlocfilehash: 98997bfbb7d3c9343f78438b1195222565c5b9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444551"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="cf88f-102">Metodo IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="cf88f-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="cf88f-103">Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.</span><span class="sxs-lookup"><span data-stu-id="cf88f-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf88f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf88f-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf88f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf88f-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="cf88f-106">[in] Un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) oggetto che identifica l'ambito importato da unire.</span><span class="sxs-lookup"><span data-stu-id="cf88f-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="cf88f-107">[in] Un puntatore a un [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) oggetto che specifica il nuovo mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="cf88f-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="cf88f-108">[in] Un puntatore a un <!--<<!--zzxref:IUnknown --> `IUnknown`>--> `IUnknown` oggetto che specifica gli errori.</span><span class="sxs-lookup"><span data-stu-id="cf88f-108">[in] A pointer to an <!--<<!--zzxref:IUnknown --> `IUnknown`>--> `IUnknown` object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf88f-109">Note</span><span class="sxs-lookup"><span data-stu-id="cf88f-109">Remarks</span></span>  
 <span data-ttu-id="cf88f-110">Chiamare [IMetaDataEmit:: MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) per attivare l'unione dei metadati in un singolo ambito.</span><span class="sxs-lookup"><span data-stu-id="cf88f-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf88f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf88f-111">Requirements</span></span>  
 <span data-ttu-id="cf88f-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf88f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf88f-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cf88f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf88f-114">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cf88f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf88f-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf88f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf88f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf88f-116">See Also</span></span>  
 [<span data-ttu-id="cf88f-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cf88f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="cf88f-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cf88f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
