---
title: Metodo IHostMemoryManager::AcquiredVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
ms.openlocfilehash: b70454cd1e2d6d38e6ca4d0ea0bd8974963c201c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136736"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>Metodo IHostMemoryManager::AcquiredVirtualAddressSpace
Notifica all'host che la Common Language Runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `startAddress`  
 in Indirizzo iniziale della memoria.  
  
 `size`  
 in Dimensione, in byte, della memoria.  
  
## <a name="remarks"></a>Note  
 Il metodo `AcquiredVirtualAddressSpace` è un metodo di callback e deve essere implementato dal writer dell'applicazione host. Viene chiamato da CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
