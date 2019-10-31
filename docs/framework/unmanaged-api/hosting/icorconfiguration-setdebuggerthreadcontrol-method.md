---
title: Metodo ICorConfiguration::SetDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 0f6a369691ab2e4e9fd2e5d9731fb1dc0a42ba11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127788"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="51112-102">Metodo ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="51112-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="51112-103">Imposta l'interfaccia di callback che i servizi di debug chiamerà come thread Common Language Runtime (CLR) vengono bloccati e sbloccati per il debug.</span><span class="sxs-lookup"><span data-stu-id="51112-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51112-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51112-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51112-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51112-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="51112-106">in Puntatore a un oggetto [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) che notifica all'host il blocco e lo sblocco dei thread dai servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="51112-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51112-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51112-107">Requirements</span></span>  
 <span data-ttu-id="51112-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51112-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51112-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51112-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51112-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51112-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51112-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51112-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51112-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51112-112">See also</span></span>

- [<span data-ttu-id="51112-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="51112-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
