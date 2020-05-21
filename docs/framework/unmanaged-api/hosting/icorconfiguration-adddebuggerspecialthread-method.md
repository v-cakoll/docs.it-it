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
ms.openlocfilehash: 8b6593ad995872f0e0014b1e8bcd8a4b576bbeaf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762428"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="2d438-102">Metodo ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="2d438-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="2d438-103">Indica ai servizi di debug che un determinato thread deve essere in grado di continuare l'esecuzione mentre nel debugger è stata arrestata un'applicazione durante gli scenari di debug gestiti o non gestiti.</span><span class="sxs-lookup"><span data-stu-id="2d438-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d438-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d438-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d438-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d438-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="2d438-106">in ID del thread a cui deve essere consentita l'esecuzione continua.</span><span class="sxs-lookup"><span data-stu-id="2d438-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d438-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2d438-107">Remarks</span></span>  
 <span data-ttu-id="2d438-108">Al thread specificato non sarà consentito eseguire codice gestito o accedere in alcun modo al runtime.</span><span class="sxs-lookup"><span data-stu-id="2d438-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="2d438-109">Un esempio di tale thread è costituito da un thread in-process per supportare i debugger di script legacy.</span><span class="sxs-lookup"><span data-stu-id="2d438-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d438-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d438-110">Requirements</span></span>  
 <span data-ttu-id="2d438-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d438-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d438-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2d438-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d438-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d438-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d438-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d438-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d438-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d438-115">See also</span></span>

- [<span data-ttu-id="2d438-116">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="2d438-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
