---
title: Funzione ExecQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecQueryWmi esegue una query per recuperare gli oggetti.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ExecQueryWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ExecQueryWmi
helpviewer_keywords: ExecQueryWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 872109cb0472a8404c492c2867429fe783f898eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="execquerywmi-function"></a>ExecQueryWmi (funzione)
Esegue una query per recuperare gli oggetti.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ExecQueryWmi (
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
[in] Una combinazione di flag che influenzano il comportamento di questa funzione. I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice: 

| Costante | Valore  | Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostato, la funzione recupera i qualificatori archiviati nello spazio dei nomi localizzata delle impostazioni locali della connessione corrente. <br/> Se non impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag determina una chiamata semisincrona. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La funzione restituisce un enumeratore forward-only. In genere, gli enumeratori forward-only sono più veloci e utilizzano meno memoria convenzionali enumeratori, ma non consentono le chiamate a [Clone](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI consente di mantenere i puntatori agli oggetti di enumration finché vengono rilasciate. | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | Assicura che qualsiasi restituiti gli oggetti dispongono sufficienti informazioni in essi contenuti in modo che le proprietà di sistema, ad esempio **Path**, **RelPath**, e **server**, non sono `null`. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Questo flag viene utilizzato per la creazione di prototipi. Non eseguire la query e restituisce un oggetto che è simile a un oggetto risultato tipico. |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | Cause accesso diretto al provider per la classe specificata, indipendentemente dalla relativa classe padre o sottoclassi. |

I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per prestazioni ottimali.

`pCtx`  
[in] In genere, questo valore è `null`. In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) istanza che può essere utilizzato dal provider che fornisce le classi di richieste. 

`ppEnum`  
[out] Se si verifica alcun errore, riceve il puntatore a un enumeratore che consente al chiamante di recuperare le istanze nel set di risultati della query. La query può avere un set di risultati con zero istanze. Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.

`authLevel`  
[in] Il livello di autorizzazione.

`impLevel`[in] Il livello di rappresentazione.

`pCurrentNamespace`   
[in] Un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto che rappresenta lo spazio dei nomi corrente.

`strUser`   
[in] Il nome utente. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

`strPassword`   
[in] La password. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

`strAuthority`   
[in] Il nome di dominio dell'utente. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone dell'autorizzazione per visualizzare uno o più classi che la funzione può restituire. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | La query contiene un errore di sintassi. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Il linguaggio di query richiesta non è supportato. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La query è troppo complessa. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente arrestato e riavviarlo. Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La query specifica una classe che non esiste. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) metodo.

Questa funzione elabora la query specificata nel `strQuery` parametro e crea un enumeratore tramite cui il chiamante può accedere i risultati della query. L'enumeratore è un puntatore a un [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interfaccia; la query risultati sono istanze di oggetti classe resi disponibili tramite il [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interfaccia.

Vi sono limiti al numero di `AND` e `OR` parole chiave che possono essere utilizzate nelle query WQL. Un numero elevato di parole chiave WQL utilizzate in una query complessa può provocare WMI restituire il `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) il codice di errore come un `HRESULT` valore. Il limite di parole chiave WQL dipende la complessità della query.

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
