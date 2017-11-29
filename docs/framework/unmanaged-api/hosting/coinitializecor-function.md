---
title: Funzione CoInitializeCor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeCor
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeCor
helpviewer_keywords: CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 119a01a33faeedc49931f3e7cbb1685b26366d0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="coinitializecor-function"></a><span data-ttu-id="af414-102">Funzione CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="af414-102">CoInitializeCor Function</span></span>
<span data-ttu-id="af414-103">`CoInitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="af414-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af414-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af414-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="af414-105">Note</span><span class="sxs-lookup"><span data-stu-id="af414-105">Remarks</span></span>  
 <span data-ttu-id="af414-106">Per inizializzare common language runtime, utilizzare [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="af414-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af414-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af414-107">Requirements</span></span>  
 <span data-ttu-id="af414-108">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="af414-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af414-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af414-109">See Also</span></span>  
 [<span data-ttu-id="af414-110">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="af414-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
