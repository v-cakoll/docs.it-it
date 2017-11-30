---
title: Metodo IMetaDataImport::EnumCustomAttributes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumCustomAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 78a642ab3c9766ba32537e24814b3b0536df67c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="a1c7b-102">Metodo IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="a1c7b-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="a1c7b-103">Enumera i token di definizione di attributo personalizzato associati al tipo specificato o un membro.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1c7b-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1c7b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1c7b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a1c7b-106">[in, out] Un puntatore all'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="a1c7b-107">[in] Un token per l'ambito di enumerazione, oppure zero per tutti gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a1c7b-108">[in] Un token per il costruttore del tipo di attributi da enumerare o `null` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="a1c7b-109">[out] Matrice di token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a1c7b-110">[in] Dimensione massima della matrice `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="a1c7b-111">[out, facoltativo] Il numero effettivo di valori token restituiti `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1c7b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1c7b-112">Return Value</span></span>  
  
|<span data-ttu-id="a1c7b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1c7b-113">HRESULT</span></span>|<span data-ttu-id="a1c7b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1c7b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a1c7b-115">`EnumCustomAttributes`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a1c7b-116">Non sono presenti attributi personalizzati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="a1c7b-117">In tal caso, `pcCustomAttributes` è zero.</span><span class="sxs-lookup"><span data-stu-id="a1c7b-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1c7b-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1c7b-118">Requirements</span></span>  
 <span data-ttu-id="a1c7b-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1c7b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1c7b-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a1c7b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1c7b-121">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1c7b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1c7b-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1c7b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c7b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1c7b-123">See Also</span></span>  
 [<span data-ttu-id="a1c7b-124">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a1c7b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a1c7b-125">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a1c7b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
