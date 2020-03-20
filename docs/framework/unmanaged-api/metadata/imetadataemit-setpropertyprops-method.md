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
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177469"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="d027d-102">Metodo IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="d027d-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="d027d-103">Imposta le funzionalità archiviate nei metadati per una proprietà definita da una precedente chiamata a [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="d027d-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d027d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d027d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="d027d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d027d-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="d027d-106">[in] Token per la proprietà da modificare</span><span class="sxs-lookup"><span data-stu-id="d027d-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="d027d-107">[in] Flag di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d027d-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="d027d-108">[in] Tipo del valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d027d-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d027d-109">[in] Valore predefinito per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d027d-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="d027d-110">[in] Numero di caratteri (Unicode) in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="d027d-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="d027d-111">[in] Metodo che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d027d-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="d027d-112">[in] Metodo che ottiene il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d027d-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="d027d-113">[in] Matrice di altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d027d-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="d027d-114">Terminare questa matrice `mdTokenNil` con un token.</span><span class="sxs-lookup"><span data-stu-id="d027d-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d027d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d027d-115">Requirements</span></span>  
 <span data-ttu-id="d027d-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d027d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d027d-117">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d027d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d027d-118">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d027d-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d027d-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d027d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d027d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d027d-120">See also</span></span>

- [<span data-ttu-id="d027d-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d027d-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d027d-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d027d-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
