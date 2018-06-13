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
ms.openlocfilehash: 5164e85ecc97de99dcc493c2ba5efa8fc3468471
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443180"
---
# <a name="mdainfo-structure"></a>Struttura MDAInfo
Vengono fornite informazioni dettagliate sul `Event_MDAFired` evento, che genera la creazione di un assistente al debug gestito (MDA).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`lpMDACaption`|Il titolo dell'Assistente al debug gestito corrente. Il titolo descrive il tipo di errore che ha generato il `Event_MDAFired` evento.|  
|`lpMDAMessage`|Il messaggio di output fornito dall'Assistente al debug gestito corrente.|  
  
## <a name="remarks"></a>Note  
 Esegue il debug che funzionano in combinazione con common language runtime (CLR) per eseguire attività quali l'identificazione delle condizioni non valide nel motore di esecuzione runtime o dump di informazioni aggiuntive sullo stato di assistenti al debug gestiti (MDA) il motore. Assistenti al debug gestito genera messaggi XML su eventi che altrimenti sarebbero difficili da rilevare. Sono particolarmente utili per il debug di transizioni tra codice gestito e gestito.  
  
 Quando viene generato un evento che attiva la creazione di un assistente al debug gestito, il runtime effettua le seguenti operazioni:  
  
-   Se l'host non ha registrato un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) istanza chiamando [ICLROnEventManager::](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) per ricevere una notifica di un `Event_MDAFired` evento, il runtime continua con relativo Per impostazione predefinita, il comportamento non sia ospitato.  
  
-   Se l'host ha registrato un gestore per questo evento, il runtime controlla per vedere se un debugger è collegato al processo. Questo caso, il debugger si interrompe il runtime. Quando il debugger continua, viene chiamato nell'host. Se è connesso alcun debugger, il runtime chiama `IActionOnCLREvent::OnEvent` e passa un puntatore a un `MDAInfo` l'istanza come il `data` parametro.  
  
 L'host può scegliere di attivare assistenti al debug gestito e di ricevere una notifica quando viene attivato un assistente al debug gestito. Ciò consente all'host la possibilità di ignorare il comportamento predefinito e di interrompere il thread gestito che ha generato l'evento, per evitare di danneggiare lo stato del processo. Per ulteriori informazioni sull'utilizzo di assistenti al debug gestito, vedere [la diagnosi di errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
