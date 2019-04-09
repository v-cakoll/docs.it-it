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
ms.openlocfilehash: b80bb7b62d3a4ffee61cc6756b7d7d02f2b074bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196203"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="07c8a-102">Metodo IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="07c8a-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="07c8a-103">Enumera i token di definizione di attributo personalizzato associati con il tipo specificato o il membro.</span><span class="sxs-lookup"><span data-stu-id="07c8a-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07c8a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="07c8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07c8a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="07c8a-106">[in, out] Un puntatore all'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="07c8a-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="07c8a-107">[in] Un token per l'ambito di enumerazione o zero per tutti gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="07c8a-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="07c8a-108">[in] Un token per il costruttore del tipo degli attributi da enumerare, o `null` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="07c8a-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="07c8a-109">[out] Matrice dei token di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="07c8a-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="07c8a-110">[in] Dimensione massima della matrice `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="07c8a-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="07c8a-111">[out, optional] Il numero effettivo di valori del token restituito nel `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="07c8a-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07c8a-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="07c8a-112">Return Value</span></span>  
  
|<span data-ttu-id="07c8a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07c8a-113">HRESULT</span></span>|<span data-ttu-id="07c8a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07c8a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` <span data-ttu-id="07c8a-115">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="07c8a-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="07c8a-116">Non sono presenti attributi personalizzati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="07c8a-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="07c8a-117">In tal caso, `pcCustomAttributes` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="07c8a-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07c8a-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07c8a-118">Requirements</span></span>  
 <span data-ttu-id="07c8a-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07c8a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07c8a-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="07c8a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07c8a-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="07c8a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="07c8a-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="07c8a-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07c8a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07c8a-123">See also</span></span>

- [<span data-ttu-id="07c8a-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="07c8a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="07c8a-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="07c8a-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
