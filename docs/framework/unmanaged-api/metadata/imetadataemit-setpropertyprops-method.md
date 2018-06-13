---
title: Metodo IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024ab8254f566e5386198fa1735af4c6b1972ca1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448036"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="0a0e9-102">Metodo IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="0a0e9-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="0a0e9-103">Imposta le funzioni archiviate nei metadati per una proprietà definita da una precedente chiamata a [metodo DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="0a0e9-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a0e9-104">Syntax</span></span>  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a0e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a0e9-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="0a0e9-106">[in] Il token per la proprietà da modificare</span><span class="sxs-lookup"><span data-stu-id="0a0e9-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="0a0e9-107">[in] Flag della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="0a0e9-108">[in] Il tipo di valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="0a0e9-109">[in] Il valore predefinito per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="0a0e9-110">[in] Il conteggio dei (Unicode) i caratteri `pValue`.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="0a0e9-111">[in] Il metodo che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="0a0e9-112">[in] Il metodo che ottiene il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="0a0e9-113">[in] Matrice di altri metodi associato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="0a0e9-114">Terminare questa matrice con un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="0a0e9-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0e9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a0e9-115">Requirements</span></span>  
 <span data-ttu-id="0a0e9-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a0e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0e9-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0a0e9-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a0e9-118">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0a0e9-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a0e9-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0e9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0e9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a0e9-120">See Also</span></span>  
 [<span data-ttu-id="0a0e9-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0a0e9-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0a0e9-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0a0e9-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
