---
title: Metodo IMetaDataTables::GetUserStringHeapSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetUserStringHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 69c78afddc50930d4390b516cece819f124a7933
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="6d167-102">Metodo IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="6d167-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="6d167-103">Ottiene le dimensioni, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="6d167-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d167-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d167-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d167-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d167-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="6d167-106">[out] Puntatore alla dimensione, in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="6d167-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d167-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d167-107">Requirements</span></span>  
 <span data-ttu-id="6d167-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d167-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d167-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6d167-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d167-110">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d167-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d167-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d167-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d167-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d167-112">See Also</span></span>  
 [<span data-ttu-id="6d167-113">IMetaDataTables (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d167-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="6d167-114">IMetaDataTables2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6d167-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
