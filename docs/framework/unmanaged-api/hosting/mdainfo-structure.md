---
title: Struttura MDAInfo
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faa6af54714f7f0b7ac91c7836673c163195d5f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656464"
---
# <a name="mdainfo-structure"></a>Struttura MDAInfo
Vengono forniti dettagli sul `Event_MDAFired` evento che attiva la creazione di un assistente al debug gestito (MDA).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`lpMDACaption`|Titolo dell'Assistente al debug gestito corrente. Il titolo descrive il tipo di errore che ha attivato il `Event_MDAFired` evento.|  
|`lpMDAMessage`|Il messaggio di output fornito dall'Assistente al debug gestito corrente.|  
  
## <a name="remarks"></a>Note  
 Esegue il debug che funzionano in combinazione con common language runtime (CLR) per eseguire attività quali l'identificazione delle condizioni non valide nel motore di esecuzione runtime o il dump delle informazioni aggiuntive sullo stato di assistenti al debug gestiti (MDA) di motore. Assistenti al debug gestito genera messaggi XML sugli eventi che altrimenti sarebbero difficili da rilevare. Sono particolarmente utili per le transizioni tra codice gestito e di debug.  
  
 Quando viene generato un evento che attiva la creazione di un assistente al debug gestito, il runtime esegue le operazioni seguenti:  
  
- Se l'host non è registrato un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) istanza chiamando [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) per ricevere una notifica di un `Event_MDAFired` evento, il runtime continua con relativo Per impostazione predefinita, il comportamento non ospitato.  
  
- Se l'host ha registrato un gestore per questo evento, il runtime controlla per verificare se un debugger è collegato al processo. Se si tratta, il runtime passa al debugger. Quando il debugger continua, viene chiamato nell'host. Se nessun debugger è collegato, il runtime chiama `IActionOnCLREvent::OnEvent` e passa un puntatore a un `MDAInfo` l'istanza come il `data` parametro.  
  
 L'host è possibile scegliere di attivare assistenti al debug gestito e di ricevere una notifica quando viene attivato un assistente al debug gestito. Ciò consente all'host di un'opportunità per ignorare il comportamento predefinito e per interrompere il thread gestito che ha generato l'evento, per impedire che danneggiare lo stato del processo. Per altre informazioni sull'uso di assistenti al debug gestito, vedere [diagnostica degli errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.idl  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
