---
title: Metodo IMetaDataTables::GetGuidHeapSize
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
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 297b8f3572f67aa5e8b17b1b94d71f59962cfe68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="f4a7d-102">Metodo IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="f4a7d-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="f4a7d-103">Ottiene le dimensioni, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="f4a7d-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4a7d-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4a7d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4a7d-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="f4a7d-106">[out] Puntatore alla dimensione, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="f4a7d-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4a7d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4a7d-107">Requirements</span></span>  
 <span data-ttu-id="f4a7d-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a7d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a7d-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4a7d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4a7d-110">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4a7d-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4a7d-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a7d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a7d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4a7d-112">See Also</span></span>  
 [<span data-ttu-id="f4a7d-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f4a7d-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f4a7d-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f4a7d-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
