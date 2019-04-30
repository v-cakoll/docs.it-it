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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050077"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="557ed-102">Metodo IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="557ed-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="557ed-103">Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="557ed-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="557ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="557ed-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="557ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="557ed-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="557ed-106">[in] Il token dell'attributo personalizzato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="557ed-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="557ed-107">[in] Un puntatore alla matrice che contiene l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="557ed-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="557ed-108">[in] Le dimensioni, in byte, dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="557ed-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="557ed-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="557ed-109">Requirements</span></span>  
 <span data-ttu-id="557ed-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="557ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="557ed-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="557ed-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="557ed-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="557ed-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="557ed-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="557ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557ed-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="557ed-114">See also</span></span>

- [<span data-ttu-id="557ed-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="557ed-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="557ed-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="557ed-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
