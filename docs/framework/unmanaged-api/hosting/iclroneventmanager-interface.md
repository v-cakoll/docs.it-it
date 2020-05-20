---
title: Interfaccia ICLROnEventManager
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703514"
---
# <a name="iclroneventmanager-interface"></a>Interfaccia ICLROnEventManager
Fornisce metodi che consentono all'host di registrare e annullare la registrazione di callback per gli eventi di Common Language Runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md)|Registra un puntatore di callback per l'evento specificato.|  
|[Metodo UnregisterActionOnEvent](iclroneventmanager-unregisteractiononevent-method.md)|Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.|  
  
## <a name="remarks"></a>Osservazioni  
 Per registrare e annullare la registrazione di callback di evento, l'host ottiene un riferimento a chiamando `ICLROnEventManager` il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> Gli eventi descritti da [EClrEvent](eclrevent-enumeration.md) possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione del CLR.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione EClrEvent](eclrevent-enumeration.md)
- [Interfaccia IActionOnCLREvent](iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
