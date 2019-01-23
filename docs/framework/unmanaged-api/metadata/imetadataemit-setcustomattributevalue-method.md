---
title: Metodo IMetaDataEmit::SetCustomAttributeValue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca5bd8716121148fa45cc9c66cdb19de79a06f47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546543"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="30321-102">Metodo IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="30321-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="30321-103">Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="30321-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30321-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30321-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30321-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30321-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="30321-106">[in] Il token dell'attributo personalizzato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="30321-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="30321-107">[in] Un puntatore alla matrice che contiene l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="30321-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="30321-108">[in] Le dimensioni, in byte, dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="30321-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30321-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30321-109">Requirements</span></span>  
 <span data-ttu-id="30321-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30321-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30321-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="30321-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30321-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="30321-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30321-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30321-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30321-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30321-114">See also</span></span>
- [<span data-ttu-id="30321-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="30321-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="30321-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="30321-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
