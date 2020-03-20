---
title: Metodo IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175785"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="87256-102">Metodo IMetaDataEmit::DefineProperty</span><span class="sxs-lookup"><span data-stu-id="87256-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="87256-103">Crea una definizione di proprietà per `get` `set` il tipo specificato, con le funzioni di accesso al metodo e e specificate e ottiene un token per tale definizione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87256-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87256-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87256-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87256-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="87256-106">[in] Token per la classe o l'interfaccia in cui viene definita la proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="87256-107">[in] Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="87256-108">[in] Flag della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="87256-109">[in] Firma della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="87256-110">[in] Numero di byte `pvSig`in .</span><span class="sxs-lookup"><span data-stu-id="87256-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="87256-111">[in] Tipo del valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="87256-112">[in] Valore predefinito per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="87256-113">[in] Numero di caratteri (Unicode) in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="87256-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="87256-114">[in] Metodo che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="87256-115">[in] Metodo che ottiene il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="87256-116">[in] Matrice di altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="87256-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="87256-117">Terminare la matrice `mdTokenNil`con un oggetto .</span><span class="sxs-lookup"><span data-stu-id="87256-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="87256-118">[fuori] Token `mdProperty` assegnato.</span><span class="sxs-lookup"><span data-stu-id="87256-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87256-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87256-119">Requirements</span></span>  
 <span data-ttu-id="87256-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87256-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87256-121">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="87256-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87256-122">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87256-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87256-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87256-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87256-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87256-124">See also</span></span>

- [<span data-ttu-id="87256-125">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="87256-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="87256-126">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="87256-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
