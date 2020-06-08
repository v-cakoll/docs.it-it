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
ms.openlocfilehash: af226f9317b67b23e03d06614ed5b9c956939c22
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503419"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="3222b-102">Metodo IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="3222b-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="3222b-103">Ottiene un enumeratore per una matrice di vincoli di parametri generici associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="3222b-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3222b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3222b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3222b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3222b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3222b-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3222b-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="3222b-107">in   Token che rappresenta il parametro generico i cui vincoli devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="3222b-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="3222b-108">out Matrice di vincoli di parametro generico da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3222b-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3222b-109">in   Numero massimo di token richiesto da inserire in `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="3222b-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="3222b-110">out Puntatore al numero di token inseriti in `rGenericParamConstraints` .</span><span class="sxs-lookup"><span data-stu-id="3222b-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3222b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3222b-111">Return Value</span></span>  
  
|<span data-ttu-id="3222b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3222b-112">HRESULT</span></span>|<span data-ttu-id="3222b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3222b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3222b-114">`EnumGenericParameterConstraints`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3222b-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3222b-115">`phEnum`non contiene elementi Member.</span><span class="sxs-lookup"><span data-stu-id="3222b-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="3222b-116">In questo caso, `pcGenericParameterConstraints` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3222b-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3222b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3222b-117">Requirements</span></span>  
 <span data-ttu-id="3222b-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3222b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3222b-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3222b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3222b-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3222b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3222b-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3222b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3222b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3222b-122">See also</span></span>

- [<span data-ttu-id="3222b-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3222b-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="3222b-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3222b-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
