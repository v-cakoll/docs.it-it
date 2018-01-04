---
title: Metodo IMetaDataEmit::DefineCustomAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineCustomAttribute
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 053601376f8b75e5469a3ef8a3d890a6c6620e28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="840e6-102">Metodo IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="840e6-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="840e6-103">Crea una definizione per un attributo personalizzato con la firma dei metadati specificato, per collegare l'oggetto specificato e ottiene un token per tale definizione di attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="840e6-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="840e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="840e6-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="840e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="840e6-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="840e6-106">[in] Il token per l'elemento proprietario.</span><span class="sxs-lookup"><span data-stu-id="840e6-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="840e6-107">[in] Token che identifica l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="840e6-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="840e6-108">[in] Un puntatore per l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="840e6-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="840e6-109">[in] Il numero di byte in `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="840e6-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="840e6-110">[out] Il `mdCustomAttribute` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="840e6-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="840e6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="840e6-111">Requirements</span></span>  
 <span data-ttu-id="840e6-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="840e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="840e6-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="840e6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="840e6-114">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="840e6-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="840e6-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="840e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="840e6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="840e6-116">See Also</span></span>  
 [<span data-ttu-id="840e6-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="840e6-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="840e6-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="840e6-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
