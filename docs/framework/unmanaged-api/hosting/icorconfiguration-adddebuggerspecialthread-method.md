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
ms.openlocfilehash: c5d6cfa3826667514eb70f9bb0df118d9ba0d07c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127824"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="4e1b5-102">Metodo ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="4e1b5-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="4e1b5-103">Indica ai servizi di debug che un determinato thread deve essere in grado di continuare l'esecuzione mentre nel debugger è stata arrestata un'applicazione durante gli scenari di debug gestiti o non gestiti.</span><span class="sxs-lookup"><span data-stu-id="4e1b5-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e1b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e1b5-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e1b5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e1b5-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="4e1b5-106">in ID del thread a cui deve essere consentita l'esecuzione continua.</span><span class="sxs-lookup"><span data-stu-id="4e1b5-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e1b5-107">Note</span><span class="sxs-lookup"><span data-stu-id="4e1b5-107">Remarks</span></span>  
 <span data-ttu-id="4e1b5-108">Al thread specificato non sarà consentito eseguire codice gestito o accedere in alcun modo al runtime.</span><span class="sxs-lookup"><span data-stu-id="4e1b5-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="4e1b5-109">Un esempio di tale thread è costituito da un thread in-process per supportare i debugger di script legacy.</span><span class="sxs-lookup"><span data-stu-id="4e1b5-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e1b5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e1b5-110">Requirements</span></span>  
 <span data-ttu-id="4e1b5-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e1b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e1b5-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e1b5-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e1b5-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e1b5-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e1b5-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e1b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1b5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e1b5-115">See also</span></span>

- [<span data-ttu-id="4e1b5-116">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e1b5-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
