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
ms.openlocfilehash: 3ecaebb9d943a3cdbb231307012b5dc3aaf000f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493402"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`Event_ClrDisabled`|Specifica un errore CLR irreversibile.|  
|`Event_DomainUnload`|Specifica lo scaricamento di un particolare <xref:System.AppDomain> .|  
|`Event_MDAFired`|Specifica che è stato generato un messaggio assistente al debug gestito (MDA).|  
|`Event_StackOverflow`|Specifica che si è verificato un errore di overflow dello stack.|  
  
## <a name="remarks"></a>Osservazioni  
 L'host può registrare callback per qualsiasi tipo di evento descritto da `EClrEvent` chiamando i metodi dell'interfaccia [ICLROnEventManager](iclroneventmanager-interface.md) . L'host ottiene un puntatore a questa interfaccia chiamando il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .  
  
 Gli `Event_CLRDisabled` `Event_DomainUnload` eventi e possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione di CLR.  
  
 L' `Event_MDAFired` evento genera la creazione di un'istanza di [MDAInfo](mdainfo-structure.md) che contiene i dettagli del messaggio dell'assistente al debug gestito. Per ulteriori informazioni su MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IActionOnCLREvent](iactiononclrevent-interface.md)
- [Interfaccia ICLRControl](iclrcontrol-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
