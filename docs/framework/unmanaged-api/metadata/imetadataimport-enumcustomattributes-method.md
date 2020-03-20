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
ms.openlocfilehash: 61b5678a546bdbadbcc6d8ee86447cb17ce72b99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175525"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="af84e-102">Metodo IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="af84e-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="af84e-103">Enumera i token di definizione di attributo personalizzati associati al tipo o al membro specificato.</span><span class="sxs-lookup"><span data-stu-id="af84e-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af84e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af84e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af84e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af84e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="af84e-106">[in, out] Puntatore all'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="af84e-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="af84e-107">[in] Token per l'ambito dell'enumerazione oppure zero per tutti gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="af84e-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="af84e-108">[in] Token per il costruttore del tipo di attributi `null` da enumerare o per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="af84e-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="af84e-109">[fuori] Matrice di token di attributo personalizzati.</span><span class="sxs-lookup"><span data-stu-id="af84e-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="af84e-110">[in] Dimensione massima della matrice `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="af84e-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="af84e-111">[out, opzionale] Numero effettivo di valori di `rCustomAttributes`token restituiti in .</span><span class="sxs-lookup"><span data-stu-id="af84e-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af84e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af84e-112">Return Value</span></span>  
  
|<span data-ttu-id="af84e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af84e-113">HRESULT</span></span>|<span data-ttu-id="af84e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af84e-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="af84e-115">`EnumCustomAttributes`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="af84e-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="af84e-116">Non sono presenti attributi personalizzati da enumerare.</span><span class="sxs-lookup"><span data-stu-id="af84e-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="af84e-117">In tal `pcCustomAttributes` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="af84e-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af84e-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af84e-118">Requirements</span></span>  
 <span data-ttu-id="af84e-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af84e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af84e-120">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af84e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af84e-121">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af84e-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af84e-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af84e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af84e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af84e-123">See also</span></span>

- [<span data-ttu-id="af84e-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="af84e-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="af84e-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="af84e-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
