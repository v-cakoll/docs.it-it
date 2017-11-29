---
title: Metodo IHostMemoryManager::NeedsVirtualAddressSpace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.NeedsVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62ceb9e5b4d5843b8e2adad344b3ffb662ab3aff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a>Metodo IHostMemoryManager::NeedsVirtualAddressSpace
Notifica all'host che common language runtime (CLR) tenterà di utilizzare la memoria specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `startAddress`  
 [in] L'indirizzo iniziale della memoria.  
  
 `size`  
 [in] Le dimensioni in byte, della memoria.  
  
## <a name="remarks"></a>Note  
 Il `NeedsVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host. Viene chiamato da CLR.  
  
 Se l'host non desidera che il Common Language Runtime utilizza la memoria specificata, può restituire un valore HRESULT E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IHostMemoryManager (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
