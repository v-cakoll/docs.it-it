---
title: Metodo IMetaDataTables::GetUserStringHeapSize
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
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b1f4f1b8c3cafb28c2b84867dbe5ac3f8424e8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="c1523-102">Metodo IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="c1523-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="c1523-103">Ottiene le dimensioni, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="c1523-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1523-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1523-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1523-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1523-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="c1523-106">[out] Puntatore alla dimensione, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="c1523-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1523-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1523-107">Requirements</span></span>  
 <span data-ttu-id="c1523-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1523-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1523-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c1523-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1523-110">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1523-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1523-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1523-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1523-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1523-112">See Also</span></span>  
 [<span data-ttu-id="c1523-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c1523-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="c1523-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c1523-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
