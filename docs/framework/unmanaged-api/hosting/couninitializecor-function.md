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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dca4fd4a4d20627bef8f7fedd5a801ba07e8e19b
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212079"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="347e5-102">Funzione CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="347e5-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="347e5-103">`CoUninitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="347e5-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="347e5-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="347e5-105">Note</span><span class="sxs-lookup"><span data-stu-id="347e5-105">Remarks</span></span>  
 <span data-ttu-id="347e5-106">Common language runtime non può essere scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="347e5-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="347e5-107">Per rimuovere completamente il runtime da un processo in esecuzione, è necessario arrestare il processo.</span><span class="sxs-lookup"><span data-stu-id="347e5-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347e5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="347e5-108">See also</span></span>
- [<span data-ttu-id="347e5-109">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="347e5-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
