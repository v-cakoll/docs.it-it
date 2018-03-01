---
title: Metodo IMetaDataImport::GetPropertyProps
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d838f43b500ac3dd0c3b44d9d84dd9fc039c6e16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="04aa0-102">Metodo IMetaDataImport::GetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="04aa0-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="04aa0-103">Ottiene i metadati per la proprietà rappresentata dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="04aa0-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04aa0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04aa0-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="04aa0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="04aa0-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="04aa0-106">[in] Un token che rappresenta la proprietà per restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="04aa0-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="04aa0-107">[out] Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="04aa0-108">[out] Un buffer contenente il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="04aa0-109">[in] La dimensione in caratteri "wide" di `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="04aa0-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="04aa0-110">[out] Il numero di caratteri "wide" restituiti in `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="04aa0-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="04aa0-111">[out] Puntatore ai flag di attributo applicato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="04aa0-112">Questo valore è una maschera di bit di [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="04aa0-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="04aa0-113">[out] Un puntatore per la firma dei metadati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="04aa0-114">[out] Il numero di byte restituiti nella `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="04aa0-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="04aa0-115">[out] Flag che specificano il tipo della costante che rappresenta il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="04aa0-116">Questo valore è un'enumerazione CorElementType.</span><span class="sxs-lookup"><span data-stu-id="04aa0-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="04aa0-117">[out] Puntatore ai byte archiviare il valore predefinito per questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="04aa0-118">[out] La dimensione in caratteri "wide" di `ppDefaultValue`, se `pdwCPlusTypeFlag` è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è rilevante.</span><span class="sxs-lookup"><span data-stu-id="04aa0-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="04aa0-119">In questo caso, la lunghezza di `ppDefaultValue` viene dedotto dal tipo specificato da `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="04aa0-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="04aa0-120">[out] Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="04aa0-121">[out] Puntatore al token MethodDef che rappresenta il metodo di funzione di accesso get della proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="04aa0-122">[out] Matrice di token MethodDef che rappresentano gli altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="04aa0-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="04aa0-123">[in] Dimensione massima della matrice `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="04aa0-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="04aa0-124">Se non si specifica una matrice sufficientemente grande da contenere tutti i metodi, questi verranno ignorati senza avviso.</span><span class="sxs-lookup"><span data-stu-id="04aa0-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="04aa0-125">[out] Il numero di token MethodDef restituiti in `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="04aa0-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04aa0-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04aa0-126">Requirements</span></span>  
 <span data-ttu-id="04aa0-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04aa0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04aa0-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="04aa0-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04aa0-129">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04aa0-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04aa0-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04aa0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04aa0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04aa0-131">See Also</span></span>  
 [<span data-ttu-id="04aa0-132">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="04aa0-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="04aa0-133">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="04aa0-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
