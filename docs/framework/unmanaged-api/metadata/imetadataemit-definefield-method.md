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
ms.openlocfilehash: ccc4843864f375c167acdb12575c282dbe3a49e1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004816"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="f4bee-102">Metodo IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="f4bee-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="f4bee-103">Crea una definizione per un campo con la firma dei metadati specificata e ottiene un token per la definizione del campo.</span><span class="sxs-lookup"><span data-stu-id="f4bee-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4bee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4bee-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f4bee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4bee-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f4bee-106">in `mdTypeDef`Token per la classe o l'interfaccia contenitore.</span><span class="sxs-lookup"><span data-stu-id="f4bee-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="f4bee-107">in Nome del campo in Unicode.</span><span class="sxs-lookup"><span data-stu-id="f4bee-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="f4bee-108">in Attributi del campo.</span><span class="sxs-lookup"><span data-stu-id="f4bee-108">[in] The field attributes.</span></span> <span data-ttu-id="f4bee-109">Si tratta di una maschera di maschera di `CorFieldAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="f4bee-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f4bee-110">in Firma del campo sotto forma di BLOB.</span><span class="sxs-lookup"><span data-stu-id="f4bee-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f4bee-111">in Numero di byte in `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="f4bee-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f4bee-112">in Oggetto `ELEMENT_TYPE_` *\** per il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="f4bee-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="f4bee-113">Si tratta di un `CorElementType` valore.</span><span class="sxs-lookup"><span data-stu-id="f4bee-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="f4bee-114">Se non si definisce un valore costante per il campo, usare `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="f4bee-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f4bee-115">in Valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="f4bee-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f4bee-116">in Dimensione in (Unicode) dei caratteri di `pValue` .</span><span class="sxs-lookup"><span data-stu-id="f4bee-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="f4bee-117">out `mdFieldDef`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="f4bee-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4bee-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4bee-118">Requirements</span></span>  
 <span data-ttu-id="f4bee-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4bee-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4bee-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4bee-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4bee-121">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4bee-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4bee-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4bee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4bee-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4bee-123">See also</span></span>

- [<span data-ttu-id="f4bee-124">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f4bee-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f4bee-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f4bee-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
