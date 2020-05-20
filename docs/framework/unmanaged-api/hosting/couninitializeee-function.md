---
title: Funzione CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616463"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="96d07-102">Funzione CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="96d07-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="96d07-103">`CoUninitializeEE`è obsoleto e non fornisce alcuna funzionalità.</span><span class="sxs-lookup"><span data-stu-id="96d07-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96d07-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="96d07-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="96d07-105">Remarks</span></span>  
 <span data-ttu-id="96d07-106">Il motore di esecuzione Common Language Runtime non può essere scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="96d07-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="96d07-107">Per arrestare il motore di esecuzione, chiamare [CorExitProcess](corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="96d07-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d07-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96d07-108">See also</span></span>

- [<span data-ttu-id="96d07-109">Funzione CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="96d07-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="96d07-110">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="96d07-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
