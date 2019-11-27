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
ms.openlocfilehash: 247a2793bf3806f5ee38585d50b4535820dfcb69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437066"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="05d92-102">Metodo IMetaDataImport::GetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="05d92-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="05d92-103">Ottiene i metadati per la proprietà rappresentata dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="05d92-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05d92-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="05d92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05d92-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="05d92-106">in Token che rappresenta la proprietà per la quale restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="05d92-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="05d92-107">out Puntatore al token TypeDef che rappresenta il tipo che implementa la proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="05d92-108">out Buffer in cui memorizzare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="05d92-109">in Dimensioni in caratteri wide di `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="05d92-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="05d92-110">out Numero di caratteri wide restituiti in `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="05d92-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="05d92-111">out Puntatore a qualsiasi flag di attributo applicato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="05d92-112">Questo valore è una maschera di maschera dall'enumerazione [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="05d92-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="05d92-113">out Puntatore alla firma dei metadati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="05d92-114">out Numero di byte restituiti in `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="05d92-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="05d92-115">out Flag che specifica il tipo della costante che corrisponde al valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="05d92-116">Questo valore è dall'enumerazione CorElementType.</span><span class="sxs-lookup"><span data-stu-id="05d92-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="05d92-117">out Puntatore ai byte in cui è archiviato il valore predefinito per questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="05d92-118">out Dimensioni in caratteri wide di `ppDefaultValue`, se `pdwCPlusTypeFlag` è ELEMENT_TYPE_STRING; in caso contrario, questo valore non è pertinente.</span><span class="sxs-lookup"><span data-stu-id="05d92-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="05d92-119">In tal caso, la lunghezza di `ppDefaultValue` viene dedotta dal tipo specificato da `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="05d92-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="05d92-120">out Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso set per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="05d92-121">out Puntatore al token MethodDef che rappresenta il metodo della funzione di accesso get per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="05d92-122">out Matrice di token MethodDef che rappresentano altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="05d92-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="05d92-123">[in] Dimensione massima della matrice `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="05d92-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="05d92-124">Se non si specifica una matrice sufficientemente grande da conservare tutti i metodi, verranno ignorati senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="05d92-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="05d92-125">out Numero di token MethodDef restituiti in `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="05d92-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d92-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05d92-126">Requirements</span></span>  
 <span data-ttu-id="05d92-127">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d92-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d92-128">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="05d92-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05d92-129">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="05d92-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05d92-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d92-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d92-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05d92-131">See also</span></span>

- [<span data-ttu-id="05d92-132">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="05d92-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="05d92-133">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="05d92-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
