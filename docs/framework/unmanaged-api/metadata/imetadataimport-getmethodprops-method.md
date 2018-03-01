---
title: Metodo IMetaDataImport::GetMethodProps
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
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="ff9e1-102">Metodo IMetaDataImport::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="ff9e1-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="ff9e1-103">Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff9e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff9e1-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff9e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff9e1-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ff9e1-106">[in] Il token MethodDef che rappresenta il metodo per restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="ff9e1-107">[out] Un puntatore a un token TypeDef che rappresenta il tipo che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="ff9e1-108">[out] Puntatore a un buffer con il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="ff9e1-109">[in] La dimensione richiesta del `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="ff9e1-110">[out] Un puntatore alla dimensione in caratteri "wide" di `szMethod`, o in caso di troncamento, il numero effettivo di caratteri "wide" nel nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="ff9e1-111">[out] Puntatore a tutti i flag associati al metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="ff9e1-112">[out] Un puntatore per la firma binaria dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="ff9e1-113">[out] Un puntatore alla dimensione in byte di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="ff9e1-114">[out] Un puntatore all'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="ff9e1-115">[out] Puntatore ai flag di implementazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="ff9e1-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff9e1-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff9e1-116">Requirements</span></span>  
 <span data-ttu-id="ff9e1-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff9e1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff9e1-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ff9e1-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff9e1-119">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff9e1-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff9e1-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff9e1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9e1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff9e1-121">See Also</span></span>  
 [<span data-ttu-id="ff9e1-122">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ff9e1-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ff9e1-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ff9e1-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
