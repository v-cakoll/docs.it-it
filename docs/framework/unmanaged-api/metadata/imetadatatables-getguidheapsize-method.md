---
title: Metodo IMetaDataTables::GetGuidHeapSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetGuidHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76a2aa4495a9f34a57c8a84ec40ab946abc64532
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="492aa-102">Metodo IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="492aa-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="492aa-103">Ottiene le dimensioni, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="492aa-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="492aa-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="492aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="492aa-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="492aa-106">[out] Puntatore alla dimensione, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="492aa-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="492aa-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="492aa-107">Requirements</span></span>  
 <span data-ttu-id="492aa-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="492aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="492aa-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="492aa-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="492aa-110">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="492aa-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="492aa-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492aa-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="492aa-112">See Also</span></span>  
 [<span data-ttu-id="492aa-113">IMetaDataTables (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="492aa-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="492aa-114">IMetaDataTables2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="492aa-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
