---
title: Metodo IMetaDataImport2::EnumGenericParams
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumGenericParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0e6a5dc6cd1d82a3ccd46b09e301a84f90a3f429
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="e70bb-102">Metodo IMetaDataImport2::EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="e70bb-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="e70bb-103">Ottiene un enumeratore per una matrice di token di parametri generici associati il TypeDef o MethodDef specificato token.</span><span class="sxs-lookup"><span data-stu-id="e70bb-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e70bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e70bb-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e70bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e70bb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e70bb-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="e70bb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="e70bb-107">[in] Il token TypeDef o MethodDef i cui parametri generici sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="e70bb-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="e70bb-108">[out] Matrice di parametri generici da enumerare.</span><span class="sxs-lookup"><span data-stu-id="e70bb-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e70bb-109">[in] Il numero massimo di richiesto di token da inserire `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="e70bb-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="e70bb-110">[out] Il numero restituito di token inseriti in `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="e70bb-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e70bb-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e70bb-111">Return Value</span></span>  
  
|<span data-ttu-id="e70bb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e70bb-112">HRESULT</span></span>|<span data-ttu-id="e70bb-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e70bb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e70bb-114">`EnumGenericParams`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e70bb-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e70bb-115">`phEnum`non sono membri.</span><span class="sxs-lookup"><span data-stu-id="e70bb-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="e70bb-116">In questo caso, `pcGenericParams` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="e70bb-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e70bb-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e70bb-117">Requirements</span></span>  
 <span data-ttu-id="e70bb-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e70bb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e70bb-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e70bb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e70bb-120">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e70bb-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e70bb-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e70bb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70bb-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e70bb-122">See Also</span></span>  
 [<span data-ttu-id="e70bb-123">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e70bb-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="e70bb-124">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e70bb-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
