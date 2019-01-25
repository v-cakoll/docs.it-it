---
title: Metodo IHostMemoryManager::NeedsVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4a67e1eb5a257cc6d4e4c9bc8798b61c97fba38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661750"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a>Metodo IHostMemoryManager::NeedsVirtualAddressSpace
Notifica all'host che common language runtime (CLR) sta per tentare di utilizzare la memoria specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `startAddress`  
 [in] Indirizzo iniziale della memoria.  
  
 `size`  
 [in] Le dimensioni, in byte, della memoria.  
  
## <a name="remarks"></a>Note  
 Il `NeedsVirtualAddressSpace` metodo è un metodo di callback e devono essere implementato dal writer dell'applicazione host. Viene chiamato da Common Language Runtime.  
  
 Se l'host non desidera che il Common Language Runtime utilizza la memoria specificata, può restituire un valore HRESULT E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
