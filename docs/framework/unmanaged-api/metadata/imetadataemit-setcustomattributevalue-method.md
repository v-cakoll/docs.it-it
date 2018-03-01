---
title: Metodo IMetaDataEmit::SetCustomAttributeValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6900fe9edd8c551952691ab02042e5172a39d626
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="1a5f5-102">Metodo IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="1a5f5-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="1a5f5-103">Imposta o aggiorna il valore di un attributo personalizzato definito tramite una chiamata precedente a [IMetaDataEmit:: DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="1a5f5-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a5f5-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a5f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a5f5-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="1a5f5-106">[in] Il token dell'attributo personalizzato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1a5f5-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="1a5f5-107">[in] Puntatore a matrice che contiene l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1a5f5-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="1a5f5-108">[in] Le dimensioni in byte, dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1a5f5-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5f5-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a5f5-109">Requirements</span></span>  
 <span data-ttu-id="1a5f5-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a5f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a5f5-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1a5f5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a5f5-112">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a5f5-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a5f5-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a5f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5f5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a5f5-114">See Also</span></span>  
 [<span data-ttu-id="1a5f5-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1a5f5-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1a5f5-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1a5f5-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
