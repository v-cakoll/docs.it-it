---
title: Funzione CoUninitializeCor
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
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
ms.openlocfilehash: 305a8d7b5a800c46ed814b1e654947859dc9bd03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427811"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="053a9-102">Funzione CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="053a9-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="053a9-103">`CoUninitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="053a9-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="053a9-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="053a9-105">Note</span><span class="sxs-lookup"><span data-stu-id="053a9-105">Remarks</span></span>  
 <span data-ttu-id="053a9-106">Common language runtime non può essere scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="053a9-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="053a9-107">Per rimuovere completamente il runtime da un processo in esecuzione, è necessario arrestare il processo.</span><span class="sxs-lookup"><span data-stu-id="053a9-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053a9-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="053a9-108">See Also</span></span>  
 [<span data-ttu-id="053a9-109">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="053a9-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
