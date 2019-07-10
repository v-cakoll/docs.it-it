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
ms.openlocfilehash: e3ce0b9a40d5375f563662d73964d28724209dcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758299"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="8de27-102">Funzione CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="8de27-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="8de27-103">`CoUninitializeCor` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8de27-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de27-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8de27-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8de27-105">Note</span><span class="sxs-lookup"><span data-stu-id="8de27-105">Remarks</span></span>  
 <span data-ttu-id="8de27-106">Common language runtime non può essere scaricato da un processo.</span><span class="sxs-lookup"><span data-stu-id="8de27-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="8de27-107">Per rimuovere completamente il runtime da un processo in esecuzione, è necessario arrestare il processo.</span><span class="sxs-lookup"><span data-stu-id="8de27-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de27-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de27-108">See also</span></span>

- [<span data-ttu-id="8de27-109">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="8de27-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
