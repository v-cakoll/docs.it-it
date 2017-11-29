---
title: Metodo IMetaDataImport2::GetGenericParamProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af6ab8fd6e941f5219c1aad2946479dda0b64264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="46f09-102">Metodo IMetaDataImport2::GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="46f09-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="46f09-103">Ottiene i metadati associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="46f09-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f09-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46f09-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46f09-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46f09-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="46f09-106">[in] Token che rappresenta il parametro generico per il quale restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="46f09-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="46f09-107">[out] La posizione ordinale del `Type` parametro nel metodo o nel costruttore padre.</span><span class="sxs-lookup"><span data-stu-id="46f09-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="46f09-108">[out] Il valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il `Type` per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="46f09-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="46f09-109">[out] Token TypeDef o MethodDef che rappresenta il proprietario del parametro.</span><span class="sxs-lookup"><span data-stu-id="46f09-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="46f09-110">[out] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="46f09-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="46f09-111">[out] Il nome del parametro generico.</span><span class="sxs-lookup"><span data-stu-id="46f09-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="46f09-112">[in] Le dimensioni del `wzName` buffer.</span><span class="sxs-lookup"><span data-stu-id="46f09-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="46f09-113">[out] Le dimensioni restituite del nome, in caratteri wide.</span><span class="sxs-lookup"><span data-stu-id="46f09-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f09-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46f09-114">Requirements</span></span>  
 <span data-ttu-id="46f09-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46f09-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f09-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="46f09-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46f09-117">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46f09-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46f09-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46f09-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f09-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46f09-119">See Also</span></span>  
 [<span data-ttu-id="46f09-120">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="46f09-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="46f09-121">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="46f09-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
