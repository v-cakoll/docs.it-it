---
title: Metodo IMetaDataTables::GetBlobHeapSize
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076455"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="5b625-102">Metodo IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="5b625-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="5b625-103">Ottiene la dimensione, espressa in byte, dell'heap oggetto binario di grandi dimensioni (BLOB).</span><span class="sxs-lookup"><span data-stu-id="5b625-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b625-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b625-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="5b625-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b625-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="5b625-106">[out] Un puntatore alla dimensione, espressa in byte, dell'heap dei BLOB.</span><span class="sxs-lookup"><span data-stu-id="5b625-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b625-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b625-107">Requirements</span></span>  
 <span data-ttu-id="5b625-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b625-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b625-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5b625-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b625-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5b625-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b625-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b625-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b625-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b625-112">See also</span></span>

- [<span data-ttu-id="5b625-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="5b625-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5b625-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="5b625-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
