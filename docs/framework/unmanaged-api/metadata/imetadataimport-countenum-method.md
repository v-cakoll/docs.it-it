---
title: Metodo IMetaDataImport::CountEnum
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
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26e826417e6fb48eb261278988bc7c351ee663aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="95f91-102">Metodo IMetaDataImport::CountEnum</span><span class="sxs-lookup"><span data-stu-id="95f91-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="95f91-103">Ottiene il numero di elementi nell'enumerazione recuperati dall'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="95f91-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95f91-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95f91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95f91-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="95f91-106">[in] Handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="95f91-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="95f91-107">[out] Il numero di elementi enumerati.</span><span class="sxs-lookup"><span data-stu-id="95f91-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95f91-108">Note</span><span class="sxs-lookup"><span data-stu-id="95f91-108">Remarks</span></span>  
 <span data-ttu-id="95f91-109">L'handle specificato dal `hEnum` viene ottenuto da un precedente `Enum` *nome* chiamata (ad esempio, [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="95f91-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f91-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95f91-110">Requirements</span></span>  
 <span data-ttu-id="95f91-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95f91-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f91-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95f91-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95f91-113">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95f91-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95f91-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f91-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f91-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95f91-115">See Also</span></span>  
 [<span data-ttu-id="95f91-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="95f91-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="95f91-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="95f91-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
