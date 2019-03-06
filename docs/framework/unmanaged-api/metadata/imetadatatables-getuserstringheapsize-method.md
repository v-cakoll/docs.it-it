---
title: Metodo IMetaDataTables::GetUserStringHeapSize
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1215da0816c1fc7cdfaee0da167118909f8e5eb3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466102"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="e92ea-102">Metodo IMetaDataTables::GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="e92ea-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="e92ea-103">Ottiene la dimensione, espressa in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="e92ea-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e92ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e92ea-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e92ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e92ea-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="e92ea-106">[out] Un puntatore alla dimensione, espressa in byte, dell'heap delle stringhe utente.</span><span class="sxs-lookup"><span data-stu-id="e92ea-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e92ea-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e92ea-107">Requirements</span></span>  
 <span data-ttu-id="e92ea-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e92ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e92ea-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e92ea-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e92ea-110">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e92ea-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e92ea-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e92ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92ea-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e92ea-112">See also</span></span>
- [<span data-ttu-id="e92ea-113">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e92ea-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="e92ea-114">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e92ea-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
