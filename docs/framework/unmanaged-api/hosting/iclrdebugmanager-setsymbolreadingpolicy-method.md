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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2921484cb2baa92593ddb0335cf7b20c5c0f33eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773016"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="f3504-102">Metodo ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="f3504-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="f3504-103">Imposta i criteri per la lettura dei file di programma (PDB) del database.</span><span class="sxs-lookup"><span data-stu-id="f3504-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="f3504-104">Il criterio determina se le informazioni sui file e i numeri di riga viene inclusa negli stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="f3504-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3504-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3504-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3504-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3504-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="f3504-107">[in] Un membro del [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f3504-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3504-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3504-108">Return Value</span></span>  
  
|<span data-ttu-id="f3504-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3504-109">HRESULT</span></span>|<span data-ttu-id="f3504-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3504-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3504-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3504-111">S_OK</span></span>|<span data-ttu-id="f3504-112">`SetSymbolReadingPolicy` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f3504-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="f3504-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3504-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3504-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f3504-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f3504-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3504-115">E_FAIL</span></span>|<span data-ttu-id="f3504-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f3504-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f3504-117">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f3504-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f3504-118">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3504-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3504-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3504-119">Requirements</span></span>  
 <span data-ttu-id="f3504-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3504-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3504-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f3504-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3504-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f3504-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3504-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3504-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3504-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3504-124">See also</span></span>

- [<span data-ttu-id="f3504-125">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="f3504-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
