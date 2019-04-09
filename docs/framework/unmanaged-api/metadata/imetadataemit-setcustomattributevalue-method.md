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
ms.openlocfilehash: 6f9e684b90dcc7f0ff83962361486caf7e991568
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096342"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="c7ce7-102">Metodo IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="c7ce7-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="c7ce7-103">Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="c7ce7-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ce7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7ce7-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7ce7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7ce7-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="c7ce7-106">[in] Il token dell'attributo personalizzato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="c7ce7-107">[in] Un puntatore alla matrice che contiene l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="c7ce7-108">[in] Le dimensioni, in byte, dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ce7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7ce7-109">Requirements</span></span>  
 <span data-ttu-id="c7ce7-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ce7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ce7-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c7ce7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7ce7-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c7ce7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c7ce7-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c7ce7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7ce7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7ce7-114">See also</span></span>

- [<span data-ttu-id="c7ce7-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c7ce7-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c7ce7-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c7ce7-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
