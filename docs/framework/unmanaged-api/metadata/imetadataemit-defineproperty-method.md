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
ms.openlocfilehash: 479cb25ad8e1c263d3539a4203ac5bea781eb931
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009379"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="bcfd6-102">Metodo IMetaDataEmit::DefineProperty</span><span class="sxs-lookup"><span data-stu-id="bcfd6-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="bcfd6-103">Crea una definizione di proprietà per il tipo specificato, con le `get` funzioni di accesso ai metodi e specificate `set` , e ottiene un token per la definizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfd6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcfd6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bcfd6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcfd6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bcfd6-106">in Token per la classe o l'interfaccia in cui viene definita la proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="bcfd6-107">[in] Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="bcfd6-108">in Flag della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="bcfd6-109">in Firma della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="bcfd6-110">in Numero di byte in `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="bcfd6-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="bcfd6-111">in Tipo del valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="bcfd6-112">in Valore predefinito per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="bcfd6-113">in Numero di caratteri (Unicode) in `pValue` .</span><span class="sxs-lookup"><span data-stu-id="bcfd6-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="bcfd6-114">in Metodo che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="bcfd6-115">in Metodo che ottiene il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="bcfd6-116">in Matrice di altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="bcfd6-117">Terminare la matrice con un oggetto `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="bcfd6-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="bcfd6-118">out `mdProperty`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfd6-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcfd6-119">Requirements</span></span>  
 <span data-ttu-id="bcfd6-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcfd6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfd6-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bcfd6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bcfd6-122">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bcfd6-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcfd6-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfd6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfd6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcfd6-124">See also</span></span>

- [<span data-ttu-id="bcfd6-125">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bcfd6-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="bcfd6-126">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bcfd6-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
