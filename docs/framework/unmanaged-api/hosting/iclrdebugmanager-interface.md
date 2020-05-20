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
ms.openlocfilehash: 717a3d12528a34eafbd918c29d8e13bb87097d82
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615776"
---
# <a name="iclrdebugmanager-interface"></a>Interfaccia ICLRDebugManager
Fornisce metodi che consentono a un host di associare un set di attività con un identificatore e un nome descrittivo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginConnection](iclrdebugmanager-beginconnection-method.md)|Stabilisce una nuova connessione tra l'host e il debugger per associare le attività a un identificatore e un nome descrittivo.|  
|[Metodo EndConnection](iclrdebugmanager-endconnection-method.md)|Rimuove l'associazione tra un elenco di attività e un identificatore e un nome descrittivo.|  
|[Metodo GetDacl](iclrdebugmanager-getdacl-method.md)|Questo metodo non è implementato.|  
|[Metodo IsDebuggerAttached](iclrdebugmanager-isdebuggerattached-method.md)|Ottiene un valore che indica se un debugger è collegato al processo.|  
|[Metodo SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Associa un elenco di istanze di [ICLRTask](iclrtask-interface.md) a un identificatore e a un nome descrittivo.|  
|[Metodo SetDacl](iclrdebugmanager-setdacl-method.md)|Questo metodo non è implementato.|  
|[Metodo SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md)|Imposta i criteri per la lettura dei file di database di programma (PDB). Il criterio determina se le informazioni sui numeri di riga e sui file sono incluse negli stack di chiamate.|  
  
## <a name="remarks"></a>Osservazioni  
 Negli scenari di debug, un host potrebbe voler raggruppare le attività in base alla propria logica di programmazione. Un raggruppamento, ad esempio, consente a uno sviluppatore di visualizzare solo le attività richieste dalle API dello sviluppatore, anziché visualizzare tutte le attività in esecuzione nel processo. `ICLRDebugManager`consente all'host di implementare questo tipo di raggruppamento.  
  
> [!IMPORTANT]
> Tre `ICLRDebugManager` metodi, `BeginConnection` , `SetConnectionTasks` e `EndConnection` , dipendono l'uno dall'altro. Devono essere chiamati nell'ordine specificato per funzionare come previsto.  
  
 Il raggruppamento e gli identificatori e i nomi descrittivi assegnati dall'host al raggruppamento non hanno significato per il Common Language Runtime (CLR). CLR passa semplicemente le informazioni insieme al debugger.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
