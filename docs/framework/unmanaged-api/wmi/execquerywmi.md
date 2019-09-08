---
title: Funzione ExecQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecQueryWmi esegue una query per recuperare gli oggetti.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8547d306819e85b838f1160d9912dd43e42f2f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798679"
---
# <a name="execquerywmi-function"></a>Funzione ExecQueryWmi

Esegue una query per il recupero di oggetti.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
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

`strQueryLanguage`\
in Stringa con il linguaggio di query valido supportato da gestione Windows. Deve essere "WQL", l'acronimo di WMI Query Language.

`strQuery`\
in Testo della query. Questo parametro non può `null`essere.

`lFlags`\
in Combinazione di flag che influiscono sul comportamento di questa funzione. I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

| Costante | Value  | Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostata, la funzione recupera i qualificatori modificati archiviati nello spazio dei nomi localizzato delle impostazioni locali della connessione corrente. <br/> Se non è impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag causa una chiamata semisincrono. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La funzione restituisce un enumeratore di sola trasmissione. In genere, gli enumeratori di sola trasmissione sono più veloci e utilizzano meno memoria rispetto agli enumeratori convenzionali, ma non consentono le chiamate da [clonare](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI mantiene i puntatori agli oggetti nell'enumerazione fino a quando non vengono rilasciati. |
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | Garantisce che tutti gli oggetti restituiti dispongano di informazioni sufficienti in modo che le proprietà di sistema, ad esempio **__PATH**, **__RELPATH**e **__SERVER**, non `null`lo siano. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Questo flag viene usato per la realizzazione di prototipi. Non esegue la query e restituisce invece un oggetto simile a un oggetto risultato tipico. |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | Causa l'accesso diretto al provider per la classe specificata senza considerare la relativa classe padre o qualsiasi sottoclasse. |

I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per ottenere prestazioni ottimali.

`pCtx`\
in In genere, questo valore `null`è. In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.

`ppEnum`\
out Se non si verificano errori, riceve il puntatore all'enumeratore che consente al chiamante di recuperare le istanze nel set di risultati della query. La query può avere un set di risultati con zero istanze. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

`authLevel`\
in Livello di autorizzazione.

`impLevel`\
in Livello di rappresentazione.

`pCurrentNamespace`\
in Puntatore a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) che rappresenta lo spazio dei nomi corrente.

`strUser`\
in Nome utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

`strPassword`\
in Password. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

`strAuthority`\
in Nome di dominio dell'utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone delle autorizzazioni necessarie per visualizzare una o più classi che la funzione può restituire. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Errore di sintassi della query. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Il linguaggio di query richiesto non è supportato. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La query è troppo complessa. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente interrotto e riavviato. Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La query specifica una classe che non esiste. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) .

Questa funzione elabora la query specificata nel `strQuery` parametro e crea un enumeratore tramite il quale il chiamante può accedere ai risultati della query. L'enumeratore è un puntatore a un'interfaccia [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) . i risultati della query sono istanze di oggetti della classe resi disponibili tramite l'interfaccia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

Sono previsti limiti al numero di `AND` parole chiave e `OR` che è possibile utilizzare nelle query WQL. Un numero elevato di parole chiave WQL utilizzate in una query complessa può causare la restituzione del `WBEM_E_QUOTA_VIOLATION` codice di errore (o 0x8004106c) di WMI `HRESULT` come valore. Il limite di parole chiave WQL dipende dalla complessità della query.

Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
