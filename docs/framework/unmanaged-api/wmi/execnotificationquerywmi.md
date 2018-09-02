---
title: Funzione ExecNotificationQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecNotificationQueryWmi esegue una query per la ricezione di eventi.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d314d85e7c1297636e8dd5cecaf050a527151518
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43453051"
---
# <a name="execnotificationquerywmi-function"></a>ExecNotificationQueryWmi (funzione)
Esegue una query per la ricezione di eventi. La chiamata termina immediatamente e il chiamante può eseguire il polling dell'enumeratore restituito per gli eventi appena arrivano. Rilasciare l'enumeratore restituito Annulla la query.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>Parametri

`strQueryLanguage`    
[in] Una stringa con il linguaggio di query valida supportata dalla gestione di Windows. Deve essere "WQL", l'acronimo di WMI Query Language.

`strQuery`  
[in] Il testo della query. Questo parametro non può essere `null`.

`lFlags`   
[in] Una combinazione dei flag di due seguenti che influiscono sul comportamento di questa funzione. Questi valori sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice. 

| Costante | Valore  | Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag determina una chiamata semisincrona. Se questo flag non è impostato, la chiamata ha esito negativo. Questo avviene perché gli eventi vengono ricevuti in modo continuo, ovvero che l'utente deve eseguire il polling dell'enumeratore restituito. Questa chiamata di blocco a tempo indeterminato che rende impossibili. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La funzione restituisce un enumeratore di tipo forward-only. In genere, gli enumeratori di tipo forward-only sono più veloci e usano meno memoria rispetto a enumeratori convenzionali, ma non consentono chiamate a [Clone](clone.md). |

`pCtx`  
[in] In genere, questo valore è `null`. In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istanza che può essere utilizzata dal provider che fornisce gli eventi richiesti. 

`ppEnum`  
[out] Se si verifica alcun errore, riceve il puntatore all'enumeratore che consente al chiamante recuperare le istanze nel set di risultati della query. Vedere le [osservazioni](#remarks) sezione per altre informazioni.

`authLevel`  
[in] Il livello di autorizzazione.

`impLevel` [in] Il livello di rappresentazione.

`pCurrentNamespace`   
[in] Un puntatore a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto che rappresenta lo spazio dei nomi corrente.

`strUser`   
[in] Il nome utente. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

`strPassword`   
[in] La password. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

`strAuthority`   
[in] Il nome di dominio dell'utente. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente dispone dell'autorizzazione per visualizzare uno o più delle classi che la funzione può restituire. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La query specifica una classe che non esiste. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | È stata richiesta una quantità eccessiva precisione nel recapito di eventi. È necessario specificare una maggiore tolleranza di polling. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | Requess la query in cui è possono fornire più informazioni di gestione di Windows. Ciò `HRESULT` viene restituito quando una query di eventi comporta una richiesta per eseguire il polling di tutti gli oggetti in uno spazio dei nomi. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | La query era un errore di sintassi. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Il linguaggio della query richiesta non è supportato. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La query è troppo complessa. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente arresto e riavvio. Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | La query non può essere analizzata. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) (metodo).

Dopo la funzione termina, il chiamante passa periodicamente restituita `ppEnum` dell'oggetto per il [successivo](next.md) funzione per verificare se tutti gli eventi sono disponibili.

Sono previsti limiti al numero di `AND` e `OR` parole chiave che possono essere usate nelle query WQL. Un numero elevato di parole chiave WQL utilizzate in una query complessa può provocare WMI restituire il `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) codice di errore come un `HRESULT` valore. Il limite delle parole chiave WQL dipende complessità della query.

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
