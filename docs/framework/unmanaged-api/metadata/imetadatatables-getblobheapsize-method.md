---
title: Metodo IMetaDataTables::GetBlobHeapSize
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
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 176d924ec117365408a31f1bfc38901a7ef2cf65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="e0abe-102">Metodo IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="e0abe-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="e0abe-103">Ottiene le dimensioni, in byte di heap degli oggetti binari di grandi dimensioni (BLOB).</span><span class="sxs-lookup"><span data-stu-id="e0abe-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0abe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0abe-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0abe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0abe-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="e0abe-106">[out] Puntatore alla dimensione, in byte, dell'heap BLOB.</span><span class="sxs-lookup"><span data-stu-id="e0abe-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0abe-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0abe-107">Requirements</span></span>  
 <span data-ttu-id="e0abe-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0abe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0abe-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e0abe-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0abe-110">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0abe-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0abe-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0abe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0abe-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0abe-112">See Also</span></span>  
 [<span data-ttu-id="e0abe-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e0abe-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e0abe-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e0abe-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
