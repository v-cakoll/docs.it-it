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
ms.openlocfilehash: 97d196769b549022ce498958fc34cf08df442d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447090"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="07036-102">Metodo IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="07036-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="07036-103">Ottiene le dimensioni, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="07036-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07036-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07036-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07036-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07036-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="07036-106">[out] Puntatore alla dimensione, in byte, dell'heap dei GUID.</span><span class="sxs-lookup"><span data-stu-id="07036-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07036-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07036-107">Requirements</span></span>  
 <span data-ttu-id="07036-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07036-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07036-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="07036-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07036-110">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="07036-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07036-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07036-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07036-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07036-112">See Also</span></span>  
 [<span data-ttu-id="07036-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="07036-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="07036-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="07036-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
