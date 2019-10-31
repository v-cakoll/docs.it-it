---
title: Funzione PutClassWmi (riferimenti alle API non gestite)
description: La funzione PutClassWmi crea una nuova classe o ne aggiorna una esistente.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101785"
---
# <a name="putclasswmi-function"></a>PutClassWmi (funzione)

Crea una nuova classe o ne aggiorna una esistente.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>Parametri

`pObject`\
in Puntatore a una definizione di classe valida. Deve essere inizializzata correttamente con tutti i valori di proprietà richiesti.

`lFlags`\
in Combinazione di flag che influiscono sul comportamento di questa funzione. I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostato, WMI non archivia alcun qualificatore con la versione modificata. <br> Se non è impostato, si presuppone che l'oggetto non sia localizzato e che tutti i qualificatori siano archiviati con questa istanza. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Creare la classe se non esiste oppure sovrascriverla se esiste già. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aggiornare la classe. La classe deve esistere affinché la chiamata abbia esito positivo. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Creare la classe. La chiamata ha esito negativo se la classe esiste già. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag causa una chiamata semisincrono. |
| `WBEM_FLAG_OWNER_UPDATE` | 0x10000 | I provider di push devono specificare questo flag quando si chiama `PutClassWmi` per indicare che questa classe è stata modificata. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Consente di aggiornare una classe se non sono presenti classi derivate e nessuna istanza di tale classe. Consente inoltre gli aggiornamenti in tutti i casi in cui la modifica riguarda solo i qualificatori non importanti, ad esempio il qualificatore della descrizione. Se la classe dispone di istanze o modifiche per i qualificatori importanti, l'aggiornamento avrà esito negativo. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | Consente di aggiornare le classi anche se sono presenti classi figlio purché la modifica non causi conflitti con le classi figlio. Questo flag, ad esempio, consente di aggiungere una nuova proprietà alla classe di base che non è stata citata in precedenza in nessuna delle classi figlio. Se la classe dispone di istanze, l'aggiornamento avrà esito negativo. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | forza gli aggiornamenti delle classi quando esistono classi figlio in conflitto. Questo flag, ad esempio, impone un aggiornamento se un qualificatore di classe è definito in una classe figlio e la classe di base tenta di aggiungere lo stesso qualificatore che è in conflitto con quello esistente. In modalità Force il conflitto TIS viene risolto eliminando il qualificatore in conflitto nella classe figlio. |

`pCtx`\
in In genere, questo valore è `null`. In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.

`ppCallResult`\
out Se `null`, questo parametro è inutilizzato. Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la funzione viene restituita immediatamente con `WBEM_S_NO_ERROR`. Il parametro `ppCallResult` riceve un puntatore a un nuovo oggetto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone delle autorizzazioni necessarie per creare o modificare le classi. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La classe specificata non è valida. In genere, ciò indica che `pObject` specifica un oggetto istanza. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | Il nome della classe specificato non è valido. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | È stato effettuato un tentativo di apportare una modifica che invalida una sottoclasse. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Il flag di `WBEM_FLAG_CREATE_ONLY` è stato specificato, ma la classe esiste già. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` è stato specificato in `lFlags`e la classe non è stata trovata. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | Le proprietà obbligatorie per le classi non sono state impostate. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente interrotto e riavviato. Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices::P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) .

L'utente non può creare classi con nomi che iniziano o terminano con un carattere di sottolineatura.

Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
