---
title: Metodo IMetaDataEmit::SetParent
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
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ede8541cbf0f5d66c4d6c4ecf3bd7fee8e296038
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="9ed4e-102">Metodo IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="9ed4e-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="9ed4e-103">Stabilisce che il membro specificato, come definito da una precedente chiamata a [IMetaDataEmit:: DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), è un membro del tipo specificato, come definito da una precedente chiamata a [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ed4e-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ed4e-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ed4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ed4e-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="9ed4e-106">[in] Il `mdMemberRef` token per la ricezione di un nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9ed4e-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="9ed4e-107">[in] Il `mdToken` per il nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9ed4e-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed4e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ed4e-108">Requirements</span></span>  
 <span data-ttu-id="9ed4e-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ed4e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed4e-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9ed4e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ed4e-111">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ed4e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ed4e-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed4e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed4e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed4e-113">See Also</span></span>  
 [<span data-ttu-id="9ed4e-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9ed4e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9ed4e-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9ed4e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
