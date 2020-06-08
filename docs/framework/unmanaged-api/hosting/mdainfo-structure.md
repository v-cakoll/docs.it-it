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
ms.openlocfilehash: 517e0ae7fb5d5151f94f82d9146ebbf40bad2ef9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503861"
---
# <a name="mdainfo-structure"></a>Struttura MDAInfo
Fornisce informazioni dettagliate sull' `Event_MDAFired` evento, che attiva la creazione di un assistente al debug gestito (MDA).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`lpMDACaption`|Titolo dell'assistente al debug gestito corrente. Il titolo descrive il tipo di errore che ha attivato l' `Event_MDAFired` evento.|  
|`lpMDAMessage`|Messaggio di output fornito dall'assistente al debug gestito corrente.|  
  
## <a name="remarks"></a>Osservazioni  
 Gli assistenti al debug gestito (MDA) sono strumenti di debug che interagiscono con il Common Language Runtime (CLR) per eseguire attività quali l'identificazione di condizioni non valide nel motore di esecuzione di runtime o il dump di informazioni aggiuntive sullo stato del motore. MDA generano messaggi XML sugli eventi altrimenti difficili da intercettare. Sono particolarmente utili per il debug di transizioni tra codice gestito e non gestito.  
  
 Il runtime esegue i passaggi seguenti quando viene attivato un evento che attiva la creazione di un assistente al debug gestito:  
  
- Se l'host non ha registrato un'istanza di [IActionOnCLREvent](iactiononclrevent-interface.md) chiamando [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) per ricevere una notifica di un `Event_MDAFired` evento, il runtime procede con il comportamento predefinito non ospitato.  
  
- Se l'host ha registrato un gestore per questo evento, il runtime verifica se un debugger è collegato al processo. In caso contrario, il runtime si interrompe nel debugger. Quando il debugger continua, chiama nell'host. Se non è stato collegato alcun debugger, il runtime chiama `IActionOnCLREvent::OnEvent` e passa un puntatore a un' `MDAInfo` istanza come `data` parametro.  
  
 L'host può scegliere di attivare MDA e di ricevere una notifica quando viene attivato un assistente al debug gestito. Questo consente all'host di eseguire l'override del comportamento predefinito e di interrompere il thread gestito che ha generato l'evento, per impedire che danneggi lo stato del processo. Per ulteriori informazioni sull'utilizzo di MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. idl  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di hosting](hosting-structures.md)
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
