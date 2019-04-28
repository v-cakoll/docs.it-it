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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628659"
---
# <a name="eclrevent-enumeration"></a>Enumerazione EClrEvent
Descrive gli eventi di common language runtime (CLR) per il quale l'host può registrare i callback.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`Event_ClrDisabled`|Specifica un errore irreversibile di CLR.|  
|`Event_DomainUnload`|Specifica lo scaricamento di un particolare <xref:System.AppDomain>.|  
|`Event_MDAFired`|Specifica che un messaggio al debug gestito Assistant (MDA) sia stato generato.|  
|`Event_StackOverflow`|Specifica che si è verificato un errore di overflow dello stack.|  
  
## <a name="remarks"></a>Note  
 L'host può registrare i callback per uno qualsiasi dei tipi di eventi descritti da `EClrEvent` chiamando i metodi del [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interfaccia. L'host ottiene un puntatore all'interfaccia chiamando il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) (metodo).  
  
 Il `Event_CLRDisabled` e `Event_DomainUnload` eventi possono essere generati più di una volta e da thread diversi da segnalare uno scaricamento o la disattivazione di CLR.  
  
 Il `Event_MDAFired` eventi genera la creazione di un' [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) istanza che contiene i dettagli del messaggio assistente al debug gestito. Per altre informazioni sulle assistenti al debug gestito, vedere [diagnostica degli errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
