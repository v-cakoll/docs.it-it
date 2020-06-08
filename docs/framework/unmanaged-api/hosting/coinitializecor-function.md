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
ms.openlocfilehash: 1263467fc5db92d4dd21c4f09a98af309e2c4d55
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504420"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="0842c-102">Funzione CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="0842c-102">CoInitializeCor Function</span></span>
<span data-ttu-id="0842c-103">`CoInitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="0842c-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0842c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0842c-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="0842c-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0842c-105">Remarks</span></span>  
 <span data-ttu-id="0842c-106">Per inizializzare la Common Language Runtime, utilizzare [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="0842c-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0842c-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0842c-107">Requirements</span></span>  
 <span data-ttu-id="0842c-108">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0842c-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0842c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0842c-109">See also</span></span>

- [<span data-ttu-id="0842c-110">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="0842c-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
