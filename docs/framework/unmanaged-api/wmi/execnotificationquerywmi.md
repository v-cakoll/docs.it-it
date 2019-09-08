---
title: Funzione ExecNotificationQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecNotificationQueryWmi esegue una query per ricevere eventi.
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
ms.openlocfilehash: 5cfe54c7c9b7ae707b2d3591afbd830bac171f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798641"
---
# <a name="execnotificationquerywmi-function"></a>Funzione ExecNotificationQueryWmi

Esegue una query per la ricezione di eventi. La chiamata restituisce immediatamente un risultato e il chiamante può eseguire il polling dell'enumeratore restituito per gli eventi man mano che arrivano. Se si rilascia l'enumeratore restituito, la query viene annullata.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
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

`strQueryLanguage`\
in Stringa con il linguaggio di query valido supportato da gestione Windows. Deve essere "WQL", l'acronimo di WMI Query Language.

`strQuery`\
in Testo della query. Questo parametro non può `null`essere.

`lFlags`\
in Combinazione dei due flag seguenti che influiscono sul comportamento di questa funzione. Questi valori vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice.

| Costante | Value  | Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag causa una chiamata semisincrono. Se questo flag non è impostato, la chiamata ha esito negativo. Poiché gli eventi vengono ricevuti continuamente, il che significa che l'utente deve eseguire il polling dell'enumeratore restituito. Bloccando la chiamata in modo indefinito, l'operazione non riesce. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La funzione restituisce un enumeratore di sola trasmissione. In genere, gli enumeratori di sola trasmissione sono più veloci e utilizzano meno memoria rispetto agli enumeratori convenzionali, ma non consentono le chiamate da [clonare](clone.md). |

`pCtx`\
in In genere, questo valore `null`è. In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce gli eventi richiesti.

`ppEnum`\
out Se non si verificano errori, riceve il puntatore all'enumeratore che consente al chiamante di recuperare le istanze nel set di risultati della query. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

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

|Costante  |Value  |DESCRIZIONE  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone delle autorizzazioni necessarie per visualizzare una o più classi che la funzione può restituire. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La query specifica una classe che non esiste. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | È stata richiesta una quantità eccessiva di precisione nel recapito degli eventi. È necessario specificare una maggiore tolleranza di polling. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | La query richiede più informazioni di quelle che possono essere fornite da gestione Windows. `HRESULT` Viene restituito quando una query di evento restituisce una richiesta di eseguire il polling di tutti gli oggetti in uno spazio dei nomi. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Errore di sintassi della query. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Il linguaggio di query richiesto non è supportato. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | La query è troppo complessa. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente interrotto e riavviato. Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | Impossibile analizzare la query. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) .

Dopo la restituzione della funzione, il chiamante passa periodicamente `ppEnum` l'oggetto restituito alla funzione [successiva](next.md) per verificare se sono disponibili eventi.

Sono previsti limiti al numero di `AND` parole chiave e `OR` che è possibile utilizzare nelle query WQL. Un numero elevato di parole chiave WQL utilizzate in una query complessa può causare la restituzione del `WBEM_E_QUOTA_VIOLATION` codice di errore (o 0x8004106c) di WMI `HRESULT` come valore. Il limite di parole chiave WQL dipende dalla complessità della query.

Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
