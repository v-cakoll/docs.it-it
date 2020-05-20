---
title: Metodo ICLRDebugManager::SetSymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
ms.openlocfilehash: f037e902a9f573023022c81503ea3b987cf6d424
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615753"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="2ad87-102">Metodo ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="2ad87-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="2ad87-103">Imposta i criteri per la lettura dei file di database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="2ad87-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="2ad87-104">Il criterio determina se le informazioni sui numeri di riga e sui file sono incluse negli stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="2ad87-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad87-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ad87-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ad87-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ad87-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="2ad87-107">in Membro dell'enumerazione [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2ad87-107">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ad87-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2ad87-108">Return Value</span></span>  
  
|<span data-ttu-id="2ad87-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ad87-109">HRESULT</span></span>|<span data-ttu-id="2ad87-110">Description</span><span class="sxs-lookup"><span data-stu-id="2ad87-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ad87-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ad87-111">S_OK</span></span>|<span data-ttu-id="2ad87-112">`SetSymbolReadingPolicy`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2ad87-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="2ad87-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ad87-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ad87-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2ad87-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ad87-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ad87-115">E_FAIL</span></span>|<span data-ttu-id="2ad87-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2ad87-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ad87-117">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2ad87-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ad87-118">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2ad87-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ad87-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ad87-119">Requirements</span></span>  
 <span data-ttu-id="2ad87-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad87-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad87-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2ad87-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ad87-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ad87-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ad87-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad87-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad87-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ad87-124">See also</span></span>

- [<span data-ttu-id="2ad87-125">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="2ad87-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
