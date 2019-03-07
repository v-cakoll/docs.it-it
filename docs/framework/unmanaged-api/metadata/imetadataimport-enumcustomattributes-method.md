---
title: Metodo IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7197f905c974bafc5b3892e498083f6abc18c12
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498315"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="c3a18-102">Metodo IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="c3a18-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="c3a18-103">Enumera i token di definizione di attributo personalizzato associati con il tipo specificato o il membro.</span><span class="sxs-lookup"><span data-stu-id="c3a18-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3a18-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c3a18-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3a18-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c3a18-106">[in, out] Un puntatore all'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="c3a18-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="c3a18-107">[in] Un token per l'ambito di enumerazione o zero per tutti gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c3a18-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="c3a18-108">[in] Un token per il costruttore del tipo degli attributi da enumerare, o `null` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="c3a18-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="c3a18-109">[out] Matrice dei token di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c3a18-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c3a18-110">[in] Dimensione massima della matrice `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="c3a18-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="c3a18-111">[out, optional] Il numero effettivo di valori del token restituito nel `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="c3a18-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3a18-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3a18-112">Return Value</span></span>  
  
|<span data-ttu-id="c3a18-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3a18-113">HRESULT</span></span>|<span data-ttu-id="c3a18-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a18-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c3a18-115">`EnumCustomAttributes` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3a18-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c3a18-116">Non sono presenti attributi personalizzati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="c3a18-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="c3a18-117">In tal caso, `pcCustomAttributes` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="c3a18-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3a18-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3a18-118">Requirements</span></span>  
 <span data-ttu-id="c3a18-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3a18-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3a18-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c3a18-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3a18-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c3a18-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3a18-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3a18-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a18-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3a18-123">See also</span></span>
- [<span data-ttu-id="c3a18-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c3a18-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c3a18-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c3a18-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
