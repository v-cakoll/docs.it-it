---
title: Metodo IMetaDataTables::GetGuidHeapSize
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f9a7ddb85865545698809e1865ec571f7c5e9c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674219"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="dd845-102">Metodo IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="dd845-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="dd845-103">Ottiene la dimensione, espressa in byte, dell'heap di GUID.</span><span class="sxs-lookup"><span data-stu-id="dd845-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd845-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd845-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd845-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd845-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="dd845-106">[out] Un puntatore alla dimensione, espressa in byte, dell'heap di GUID.</span><span class="sxs-lookup"><span data-stu-id="dd845-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd845-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd845-107">Requirements</span></span>  
 <span data-ttu-id="dd845-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd845-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd845-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dd845-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd845-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="dd845-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd845-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd845-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd845-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd845-112">See also</span></span>
- [<span data-ttu-id="dd845-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="dd845-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="dd845-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="dd845-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
