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
ms.openlocfilehash: d02b834b22ba7897e4939de88bc3c61c62ac2b0e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762409"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="99ee7-102">Metodo ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="99ee7-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="99ee7-103">Imposta l'interfaccia di callback che i servizi di debug chiamerà come thread Common Language Runtime (CLR) vengono bloccati e sbloccati per il debug.</span><span class="sxs-lookup"><span data-stu-id="99ee7-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ee7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99ee7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99ee7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99ee7-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="99ee7-106">in Puntatore a un oggetto [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) che notifica all'host il blocco e lo sblocco dei thread dai servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="99ee7-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ee7-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99ee7-107">Requirements</span></span>  
 <span data-ttu-id="99ee7-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ee7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ee7-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99ee7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99ee7-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="99ee7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99ee7-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ee7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ee7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99ee7-112">See also</span></span>

- [<span data-ttu-id="99ee7-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="99ee7-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
