---
title: Metodo ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db1b19c1499f7e8a126933b4d0635a0ab73e72a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218589"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="6d746-102">Metodo ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="6d746-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="6d746-103">Indica che un thread specifico deve essere consentito di continuare l'esecuzione mentre il debugger ha un'applicazione arrestata durante gli scenari di debug gestiti o per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="6d746-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d746-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d746-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d746-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d746-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="6d746-106">[in] L'ID del thread che devono essere autorizzate di continuare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6d746-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d746-107">Note</span><span class="sxs-lookup"><span data-stu-id="6d746-107">Remarks</span></span>  
 <span data-ttu-id="6d746-108">Il thread specificato non potrà essere eseguito il codice gestito o accedere al runtime in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="6d746-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="6d746-109">Un esempio di un thread di questo tipo sarebbe un thread in-process per supportare i debugger di script precedente.</span><span class="sxs-lookup"><span data-stu-id="6d746-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d746-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d746-110">Requirements</span></span>  
 <span data-ttu-id="6d746-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d746-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d746-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6d746-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d746-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6d746-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6d746-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6d746-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d746-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d746-115">See also</span></span>

- [<span data-ttu-id="6d746-116">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="6d746-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
