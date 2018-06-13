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
ms.openlocfilehash: 59b940c0dbe9462dda513e933b7360ff55a9b447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437349"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="01d37-102">Metodo ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="01d37-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="01d37-103">Indica che un determinato thread dovrebbe poter continuare l'esecuzione mentre il debugger ha un'applicazione è stata arrestata durante gli scenari di debug gestiti o ai servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="01d37-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01d37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01d37-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01d37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01d37-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="01d37-106">[in] L'ID del thread che devono essere autorizzati per continuare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="01d37-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01d37-107">Note</span><span class="sxs-lookup"><span data-stu-id="01d37-107">Remarks</span></span>  
 <span data-ttu-id="01d37-108">Il thread specificato non potrà essere eseguito codice gestito o accedere al runtime in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="01d37-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="01d37-109">Un esempio di tale thread sarebbe un thread in-process per supportare il debugger di script precedente.</span><span class="sxs-lookup"><span data-stu-id="01d37-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01d37-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01d37-110">Requirements</span></span>  
 <span data-ttu-id="01d37-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01d37-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01d37-112">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="01d37-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01d37-113">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="01d37-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01d37-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01d37-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d37-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01d37-115">See Also</span></span>  
 [<span data-ttu-id="01d37-116">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="01d37-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
