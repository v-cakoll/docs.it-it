---
title: Funzione CoUninitializeCor
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: eddc2f29da0efd9e56df710203b1d7621ffc27a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136861"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="bc821-102">Funzione CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="bc821-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="bc821-103">`CoUninitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="bc821-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc821-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc821-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="bc821-105">Note</span><span class="sxs-lookup"><span data-stu-id="bc821-105">Remarks</span></span>  
 <span data-ttu-id="bc821-106">Impossibile scaricare il Common Language Runtime da un processo.</span><span class="sxs-lookup"><span data-stu-id="bc821-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="bc821-107">Per rimuovere completamente il runtime da un processo in esecuzione, è necessario arrestare il processo.</span><span class="sxs-lookup"><span data-stu-id="bc821-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc821-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc821-108">See also</span></span>

- [<span data-ttu-id="bc821-109">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="bc821-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
