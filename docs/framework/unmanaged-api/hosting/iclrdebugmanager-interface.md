---
title: Interfaccia ICLRDebugManager
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d123177bf9f1b5eee1a2ba4d9b7f2042ddc07aa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434939"
---
# <a name="iclrdebugmanager-interface"></a>Interfaccia ICLRDebugManager
Fornisce metodi che consentono a un host associare un set di attività con un identificatore e un nome descrittivo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Stabilisce una nuova connessione tra l'host e il debugger per associare attività a un identificatore e un nome descrittivo.|  
|[Metodo EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.|  
|[Metodo GetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Questo metodo non è implementato.|  
|[Metodo IsDebuggerAttached](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Ottiene un valore che indica se un debugger è collegato al processo.|  
|[Metodo SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Associa un elenco di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanze con un identificatore e un nome descrittivo.|  
|[Metodo SetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Questo metodo non è implementato.|  
|[Metodo SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Imposta i criteri per la lettura dei file di programma (PDB) di database. Il criterio determina se le informazioni sui numeri di riga e i file sono incluso in stack di chiamate.|  
  
## <a name="remarks"></a>Note  
 Negli scenari di debug, potrebbe essere un host per raggruppare le attività in base alla propria logica di programmazione. Ad esempio, un raggruppamento consentirebbe a uno sviluppatore visualizzare solo le attività richieste dalle API dello sviluppatore, anziché visualizzare ogni attività in esecuzione nel processo. `ICLRDebugManager` consente all'host implementare questo tipo di raggruppamento.  
  
> [!IMPORTANT]
>  Tre `ICLRDebugManager` metodi, `BeginConnection`, `SetConnectionTasks` e `EndConnection`, variano in base alla loro. Devono essere chiamati nell'ordine indicato a funzionare come previsto.  
  
 Il raggruppamento e gli identificatori e nomi descrittivi che l'host viene assegnato al raggruppamento, non hanno alcun significato per common language runtime (CLR). CLR passa semplicemente le informazioni insieme al debugger.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
