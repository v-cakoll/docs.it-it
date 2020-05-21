---
title: Metodo ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762396"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="f71d9-102">Metodo ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="f71d9-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="f71d9-103">Imposta l'interfaccia di callback per la pianificazione di thread per le attività non di runtime che altrimenti verrebbero bloccate per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f71d9-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f71d9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f71d9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f71d9-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="f71d9-106">in Puntatore a un oggetto [IGCThreadControl](igcthreadcontrol-interface.md) che notifica all'host la sospensione dei thread per le attività non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f71d9-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f71d9-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f71d9-107">Remarks</span></span>  
 <span data-ttu-id="f71d9-108">L'host può scegliere all'interno del callback [IGCThreadControl:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) se ripianificare un thread.</span><span class="sxs-lookup"><span data-stu-id="f71d9-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f71d9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f71d9-109">Requirements</span></span>  
 <span data-ttu-id="f71d9-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f71d9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71d9-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f71d9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f71d9-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f71d9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f71d9-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71d9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f71d9-114">See also</span></span>

- [<span data-ttu-id="f71d9-115">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f71d9-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
