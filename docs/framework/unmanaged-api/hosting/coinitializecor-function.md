---
title: Funzione CoInitializeCor
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 188f98504fa73c4a85615a4e688bae02d966b9b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616749"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="b9dad-102">Funzione CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="b9dad-102">CoInitializeCor Function</span></span>
<span data-ttu-id="b9dad-103">`CoInitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b9dad-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9dad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9dad-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="b9dad-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b9dad-105">Remarks</span></span>  
 <span data-ttu-id="b9dad-106">Per inizializzare la Common Language Runtime, utilizzare [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="b9dad-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9dad-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9dad-107">Requirements</span></span>  
 <span data-ttu-id="b9dad-108">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9dad-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9dad-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9dad-109">See also</span></span>

- [<span data-ttu-id="b9dad-110">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="b9dad-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
