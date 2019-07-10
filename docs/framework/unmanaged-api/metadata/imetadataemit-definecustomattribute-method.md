---
title: Metodo IMetaDataEmit::DefineCustomAttribute
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 994e007eabf8b7fdcf5446d905c06eb4ab91bb3f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777684"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="11a46-102">Metodo IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="11a46-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="11a46-103">Crea una definizione per un attributo personalizzato con la firma dei metadati specificato, da associare all'oggetto specificato e ottiene un token per tale definizione di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11a46-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a46-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11a46-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a46-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11a46-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="11a46-106">[in] Il token per l'elemento proprietario.</span><span class="sxs-lookup"><span data-stu-id="11a46-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="11a46-107">[in] Il token che identifica l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11a46-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="11a46-108">[in] Un puntatore per l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11a46-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="11a46-109">[in] Il numero di byte in `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="11a46-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="11a46-110">[out] Il `mdCustomAttribute` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="11a46-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a46-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11a46-111">Requirements</span></span>  
 <span data-ttu-id="11a46-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a46-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a46-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="11a46-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11a46-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="11a46-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11a46-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a46-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a46-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11a46-116">See also</span></span>

- [<span data-ttu-id="11a46-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="11a46-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="11a46-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="11a46-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
