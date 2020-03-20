---
title: Metodo IMetaDataImport::GetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175330"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="d91d6-102">Metodo IMetaDataImport::GetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="d91d6-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="d91d6-103">Ottiene i metadati per la proprietà rappresentata dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="d91d6-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d91d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d91d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d91d6-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="d91d6-106">[in] Token che rappresenta la proprietà per cui restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="d91d6-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="d91d6-107">[fuori] Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="d91d6-108">[fuori] Un buffer per contenere il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="d91d6-109">[in] La dimensione in `szProperty`caratteri larghi di .</span><span class="sxs-lookup"><span data-stu-id="d91d6-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="d91d6-110">[fuori] Numero di caratteri di `szProperty`tipo "wide" restituiti in .</span><span class="sxs-lookup"><span data-stu-id="d91d6-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="d91d6-111">[fuori] Puntatore a tutti i flag di attributo applicati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="d91d6-112">Questo valore è una maschera di bit dall'enumerazione [CorPropertyAttr.](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="d91d6-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="d91d6-113">[fuori] Puntatore alla firma dei metadati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="d91d6-114">[fuori] Numero di byte restituiti in . `ppvSig`</span><span class="sxs-lookup"><span data-stu-id="d91d6-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="d91d6-115">[fuori] Flag che specifica il tipo della costante che è il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="d91d6-116">Questo valore deriva dall'enumerazione CorElementType.</span><span class="sxs-lookup"><span data-stu-id="d91d6-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="d91d6-117">[fuori] Puntatore ai byte che archiviano il valore predefinito per questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="d91d6-118">[fuori] La dimensione in `ppDefaultValue`caratteri `pdwCPlusTypeFlag` di tipo "wide" di , se è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è rilevante.</span><span class="sxs-lookup"><span data-stu-id="d91d6-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="d91d6-119">In tal caso, `ppDefaultValue` la lunghezza di viene dedotta `pdwCPlusTypeFlag`dal tipo specificato da .</span><span class="sxs-lookup"><span data-stu-id="d91d6-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="d91d6-120">[fuori] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="d91d6-121">[fuori] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso get per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="d91d6-122">[fuori] Matrice di token MethodDef che rappresentano altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d91d6-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d91d6-123">[in] Dimensione massima della matrice `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="d91d6-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="d91d6-124">Se non si fornisce una matrice sufficientemente grande da contenere tutti i metodi, questi vengono ignorati senza alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="d91d6-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="d91d6-125">[fuori] Numero di token MethodDef restituiti in `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="d91d6-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d91d6-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d91d6-126">Requirements</span></span>  
 <span data-ttu-id="d91d6-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d91d6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d91d6-128">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d91d6-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d91d6-129">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d91d6-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d91d6-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d91d6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91d6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d91d6-131">See also</span></span>

- [<span data-ttu-id="d91d6-132">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d91d6-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d91d6-133">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d91d6-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
