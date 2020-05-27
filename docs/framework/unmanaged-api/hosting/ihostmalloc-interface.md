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
ms.openlocfilehash: 8f4e1cd7586df7d8e2a577d26f06eaed6b2c8bb7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804609"
---
# <a name="ihostmalloc-interface"></a>Interfaccia IHostMalloc
Fornisce metodi che consentono all'Common Language Runtime (CLR) di richiedere allocazioni con granularità fine dall'heap tramite l'host.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Alloc](ihostmalloc-alloc-method.md)|Richiede che l'host allochi la quantità di memoria richiesta dall'heap.|  
|[Metodo DebugAlloc](ihostmalloc-debugalloc-method.md)|Richiede che l'host allochi la quantità di memoria richiesta dall'heap e tenga traccia anche della posizione in cui è stata allocata la memoria.|  
|[Metodo Free](ihostmalloc-free-method.md)|Libera la memoria allocata tramite il `Alloc` metodo.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR ottiene un puntatore a interfaccia a un' `IHostMalloc` istanza di chiamando il metodo [IHostMemoryManager:: CreateMAlloc](ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostMemoryManager](ihostmemorymanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
