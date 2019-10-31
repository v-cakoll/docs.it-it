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
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131140"
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`Event_ClrDisabled`|Specifica un errore CLR irreversibile.|  
|`Event_DomainUnload`|Specifica lo scaricamento di un particolare <xref:System.AppDomain>.|  
|`Event_MDAFired`|Specifica che è stato generato un messaggio assistente al debug gestito (MDA).|  
|`Event_StackOverflow`|Specifica che si è verificato un errore di overflow dello stack.|  
  
## <a name="remarks"></a>Note  
 L'host può registrare callback per uno dei tipi di evento descritti da `EClrEvent` chiamando i metodi dell'interfaccia [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) . L'host ottiene un puntatore a questa interfaccia chiamando il metodo [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .  
  
 Gli eventi `Event_CLRDisabled` e `Event_DomainUnload` possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione di CLR.  
  
 L'evento `Event_MDAFired` genera la creazione di un'istanza di [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) che contiene i dettagli del messaggio dell'assistente al debug gestito. Per ulteriori informazioni su MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
