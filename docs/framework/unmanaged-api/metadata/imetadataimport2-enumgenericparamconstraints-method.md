---
title: Metodo IMetaDataImport2::EnumGenericParamConstraints
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumGenericParamConstraints
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72f863205c0fa7f4c6b4477c9d9143d1923a5d4c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="3ce14-102">Metodo IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="3ce14-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="3ce14-103">Ottiene un enumeratore per una matrice di vincoli del parametro generico associato al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="3ce14-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ce14-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ce14-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ce14-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3ce14-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3ce14-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="3ce14-107">[in]   Token che rappresenta il parametro generico con vincoli sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3ce14-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="3ce14-108">[out] Matrice di vincoli del parametro generico da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3ce14-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3ce14-109">[in]   Il numero massimo di richiesto di token da inserire `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="3ce14-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="3ce14-110">[out] Un puntatore al numero di token inseriti in `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="3ce14-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ce14-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3ce14-111">Return Value</span></span>  
  
|<span data-ttu-id="3ce14-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ce14-112">HRESULT</span></span>|<span data-ttu-id="3ce14-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ce14-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3ce14-114">`EnumGenericParameterConstraints`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3ce14-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3ce14-115">`phEnum`non sono membri.</span><span class="sxs-lookup"><span data-stu-id="3ce14-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="3ce14-116">In questo caso, `pcGenericParameterConstraints` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3ce14-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ce14-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ce14-117">Requirements</span></span>  
 <span data-ttu-id="3ce14-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ce14-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ce14-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3ce14-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ce14-120">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ce14-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ce14-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ce14-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce14-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ce14-122">See Also</span></span>  
 [<span data-ttu-id="3ce14-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3ce14-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="3ce14-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3ce14-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
