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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de8547ed0ee83bafe4612bdcd62607fc94fb3f69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043797"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="3f660-102">Metodo IMetaDataEmit2::DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="3f660-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="3f660-103">Crea una definizione per un parametro di tipo generico e ottiene un token per tale parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="3f660-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f660-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f660-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="3f660-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f660-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3f660-106">[in] Un' `mdTypeDef` o `mdMethodDef` token che rappresenta il metodo o costruttore per cui si desidera definire un parametro generico.</span><span class="sxs-lookup"><span data-stu-id="3f660-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="3f660-107">[in] L'indice del parametro generico.</span><span class="sxs-lookup"><span data-stu-id="3f660-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="3f660-108">[in] Valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il tipo parametro generico.</span><span class="sxs-lookup"><span data-stu-id="3f660-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="3f660-109">[in] Il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="3f660-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="3f660-110">[in] Questo parametro è riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="3f660-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="3f660-111">[in] Una matrice con terminazione zero di vincoli di tipo.</span><span class="sxs-lookup"><span data-stu-id="3f660-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="3f660-112">I membri della matrice devono essere un' `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="3f660-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="3f660-113">[out] Un token che rappresenta il parametro generico.</span><span class="sxs-lookup"><span data-stu-id="3f660-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f660-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f660-114">Requirements</span></span>  
 <span data-ttu-id="3f660-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f660-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f660-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3f660-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f660-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3f660-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f660-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f660-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f660-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f660-119">See also</span></span>

- [<span data-ttu-id="3f660-120">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3f660-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3f660-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3f660-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
