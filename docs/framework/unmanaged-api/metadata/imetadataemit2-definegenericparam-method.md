---
title: Metodo IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177447"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="738fc-102">Metodo IMetaDataEmit2::DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="738fc-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="738fc-103">Crea una definizione per un parametro di tipo generico e ottiene un token per tale parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="738fc-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="738fc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="738fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="738fc-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="738fc-106">[in] Un `mdTypeDef` `mdMethodDef` o token che rappresenta il metodo o il costruttore per il quale definire un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="738fc-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="738fc-107">[in] Indice del parametro generico.</span><span class="sxs-lookup"><span data-stu-id="738fc-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="738fc-108">[in] Valore dell'enumerazione [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) che descrive il tipo per il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="738fc-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="738fc-109">[in] Nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="738fc-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="738fc-110">[in] Questo parametro è riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="738fc-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="738fc-111">[in] Matrice con terminazione zero di vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="738fc-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="738fc-112">I membri della `mdTypeDef` `mdTypeRef`matrice `mdTypeSpec` devono essere un token , o di metadati.</span><span class="sxs-lookup"><span data-stu-id="738fc-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="738fc-113">[fuori] Token che rappresenta il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="738fc-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738fc-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="738fc-114">Requirements</span></span>  
 <span data-ttu-id="738fc-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="738fc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="738fc-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="738fc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="738fc-117">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="738fc-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="738fc-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="738fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738fc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="738fc-119">See also</span></span>

- [<span data-ttu-id="738fc-120">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="738fc-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="738fc-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="738fc-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
