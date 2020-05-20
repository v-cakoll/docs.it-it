---
title: Enumerazione EClrEvent
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 388f0de26983f8bb876f40a527f60d8bc59191a3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616349"
---
# <a name="eclrevent-enumeration"></a>Enumerazione EClrEvent
Vengono descritti gli eventi di Common Language Runtime (CLR) per i quali l'host può registrare i callback.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`Event_ClrDisabled`|Specifica un errore CLR irreversibile.|  
|`Event_DomainUnload`|Specifica lo scaricamento di un particolare <xref:System.AppDomain> .|  
|`Event_MDAFired`|Specifica che è stato generato un messaggio assistente al debug gestito (MDA).|  
|`Event_StackOverflow`|Specifica che si è verificato un errore di overflow dello stack.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host può registrare callback per qualsiasi tipo di evento descritto da `EClrEvent` chiamando i metodi dell'interfaccia [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) . L'host ottiene un puntatore a questa interfaccia chiamando il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .  
  
 Gli `Event_CLRDisabled` `Event_DomainUnload` eventi e possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione di CLR.  
  
 L' `Event_MDAFired` evento genera la creazione di un'istanza di [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) che contiene i dettagli del messaggio dell'assistente al debug gestito. Per ulteriori informazioni su MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IActionOnCLREvent](iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
