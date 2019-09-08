---
title: Funzione PutInstanceWmi (riferimenti alle API non gestite)
description: La funzione PutInstanceWmi crea o aggiorna un'istanza di una classe esistente.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798378"
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi (funzione)

Crea o aggiorna un'istanza di una classe esistente. L'istanza viene scritta nel repository WMI.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>Parametri

`pInst`\
in Puntatore all'istanza da scrivere.

`lFlags`\
in Combinazione di flag che influiscono sul comportamento di questa funzione. I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |DESCRIZIONE  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostato, WMI non archivia alcun qualificatore con la **versione modificata** . <br> Se non è impostato, si presuppone che l'oggetto non sia localizzato e che tutti i qualificatori siano archiviati con questa istanza. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Creare l'istanza, se non esiste, oppure sovrascriverla se esiste già. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aggiornare l'istanza di. L'istanza deve esistere affinché la chiamata abbia esito positivo. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Creare l'istanza di. La chiamata ha esito negativo se l'istanza esiste già. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag causa una chiamata semisincrono. |

`pCtx`\
in In genere, questo valore `null`è. In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.

`ppCallResult`\
out Se `null`, questo parametro è inutilizzato. Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY` ,`WBEM_S_NO_ERROR`la funzione restituisce immediatamente. Il `ppCallResult` parametro riceve un puntatore a un nuovo oggetto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |DESCRIZIONE  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone delle autorizzazioni necessarie per aggiornare un'istanza della classe specificata. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La classe che supporta questa istanza non è valida. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | è `null` stato specificato un oggetto per una proprietà che `null`non può essere, ad esempio uno contrassegnato da un qualificatore **NOT_NULL** o **indicizzato** . |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | L'istanza specificata non è valida. (Ad esempio, la `PutInstanceWmi` chiamata a con una classe restituisce questo valore). |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Il `WBEM_FLAG_CREATE_ONLY` flag è stato specificato, ma l'istanza esiste già. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`è stato specificato `lFlags`in, ma l'istanza non esiste. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente interrotto e riavviato. Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .

La `PutInstanceWmi` funzione supporta la creazione di istanze e l'aggiornamento solo delle istanze delle classi esistenti.  A seconda della modalità di `pCtx` impostazione del parametro, vengono aggiornate alcune o tutte le proprietà dell'istanza.

Quando l'istanza a `pInst` cui fa riferimento appartiene a una sottoclasse, gestione Windows chiama tutti i provider responsabili delle classi da cui deriva la sottoclasse. Tutti questi provider devono avere esito positivo affinché `PutInstanceWmi` la richiesta originale abbia esito positivo. Il provider che supporta la classe più in alto nella gerarchia viene chiamato per primo. L'ordine di chiamata continua con la sottoclasse della classe superiore e procede dall'alto verso il basso fino a quando gestione Windows non raggiunge il provider per la classe proprietaria dell' `pInst`istanza a cui fa riferimento.
Gestione Windows non chiama i provider per nessuna delle classi figlio di un'istanza.

Quando un'applicazione deve aggiornare un'istanza che appartiene a una gerarchia di classi, `pInst` il parametro deve puntare all'istanza contenente le proprietà da modificare. Ovvero, si consideri un'istanza di destinazione che appartiene a **ClassB**. L'istanza di **ClassB** deriva da **ClassA**e **ClassA** definisce la proprietà **propa**. Se un'applicazione vuole apportare una modifica al valore di **propa** nell'istanza di **ClassB** , deve impostare `pInst` su tale istanza anziché su un'istanza di **ClassA**.

La `PutInstanceWmi` chiamata su un'istanza di una classe astratta non è consentita.

Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
