---
title: Metodo IMetaDataImport2::EnumGenericParamConstraints
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f66b0145dbaece7292d2ccad169a97fbb10b6d11
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186681"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="08291-102">Metodo IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="08291-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="08291-103">Ottiene un enumeratore per una matrice di vincoli del parametro generico associato al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="08291-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08291-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08291-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08291-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08291-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="08291-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="08291-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="08291-107">[in]   Un token che rappresenta il parametro generico il cui vincoli devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="08291-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="08291-108">[out] Matrice di vincoli del parametro generico da enumerare.</span><span class="sxs-lookup"><span data-stu-id="08291-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="08291-109">[in]   Il numero massimo di richiesto di token da inserire `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="08291-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="08291-110">[out] Un puntatore al numero di token inserito in `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="08291-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08291-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08291-111">Return Value</span></span>  
  
|<span data-ttu-id="08291-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08291-112">HRESULT</span></span>|<span data-ttu-id="08291-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08291-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="08291-114">`EnumGenericParameterConstraints` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="08291-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="08291-115">`phEnum` non ha membro elementi.</span><span class="sxs-lookup"><span data-stu-id="08291-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="08291-116">In questo caso, `pcGenericParameterConstraints` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="08291-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08291-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08291-117">Requirements</span></span>  
 <span data-ttu-id="08291-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08291-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08291-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08291-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08291-120">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="08291-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08291-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08291-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08291-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08291-122">See also</span></span>

- [<span data-ttu-id="08291-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08291-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="08291-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08291-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
