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
ms.openlocfilehash: f0b41c03f5e6e08144ae566a3543d352c168555f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472109"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="5fa4e-102">Metodo IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="5fa4e-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="5fa4e-103">Ottiene la dimensione, espressa in byte, dell'heap di GUID.</span><span class="sxs-lookup"><span data-stu-id="5fa4e-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fa4e-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fa4e-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="5fa4e-106">[out] Un puntatore alla dimensione, espressa in byte, dell'heap di GUID.</span><span class="sxs-lookup"><span data-stu-id="5fa4e-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa4e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fa4e-107">Requirements</span></span>  
 <span data-ttu-id="5fa4e-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa4e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa4e-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5fa4e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5fa4e-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5fa4e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5fa4e-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa4e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa4e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fa4e-112">See also</span></span>
- [<span data-ttu-id="5fa4e-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="5fa4e-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5fa4e-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="5fa4e-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
