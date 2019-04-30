---
title: Metodo IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8ba8a762c56a666c67b25b9ce0420099fce419a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044161"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="2cf00-102">Metodo IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="2cf00-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="2cf00-103">Crea una definizione per un campo con la firma dei metadati specificati e ottiene un token per tale definizione di campo.</span><span class="sxs-lookup"><span data-stu-id="2cf00-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cf00-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cf00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2cf00-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2cf00-106">[in] Il `mdTypeDef` token per la classe o interfaccia che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2cf00-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="2cf00-107">[in] Il nome del campo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="2cf00-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="2cf00-108">[in] Gli attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="2cf00-108">[in] The field attributes.</span></span> <span data-ttu-id="2cf00-109">Si tratta di una maschera di bit delle `CorFieldAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="2cf00-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2cf00-110">[in] La firma del campo come BLOB.</span><span class="sxs-lookup"><span data-stu-id="2cf00-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2cf00-111">[in] Il numero di byte in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="2cf00-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2cf00-112">[in] Il `ELEMENT_TYPE_` *\** per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="2cf00-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="2cf00-113">Si tratta di un `CorElementType` valore.</span><span class="sxs-lookup"><span data-stu-id="2cf00-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="2cf00-114">Se non si definisce un valore costante per il campo, usare `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="2cf00-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2cf00-115">[in] Il valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="2cf00-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2cf00-116">[in] La dimensione in caratteri (Unicode) della `pValue`.</span><span class="sxs-lookup"><span data-stu-id="2cf00-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="2cf00-117">[out] Il `mdFieldDef` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="2cf00-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf00-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cf00-118">Requirements</span></span>  
 <span data-ttu-id="2cf00-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf00-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf00-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2cf00-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cf00-121">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2cf00-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cf00-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf00-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf00-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cf00-123">See also</span></span>

- [<span data-ttu-id="2cf00-124">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2cf00-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2cf00-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2cf00-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
