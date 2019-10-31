---
title: Interfaccia IHostMalloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136769"
---
# <a name="ihostmalloc-interface"></a>Interfaccia IHostMalloc
Fornisce metodi che consentono all'Common Language Runtime (CLR) di richiedere allocazioni con granularità fine dall'heap tramite l'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Richiede che l'host allochi la quantità di memoria richiesta dall'heap.|  
|[Metodo DebugAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Richiede che l'host allochi la quantità di memoria richiesta dall'heap e tenga traccia anche della posizione in cui è stata allocata la memoria.|  
|[Metodo Free](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Libera la memoria allocata tramite il metodo `Alloc`.|  
  
## <a name="remarks"></a>Note  
 CLR ottiene un puntatore a interfaccia a un'istanza di `IHostMalloc` chiamando il metodo [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
