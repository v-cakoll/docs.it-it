---
title: Funzione PutClassWmi (riferimenti alle API non gestite)
description: La funzione PutClassWmi crea una nuova classe o ne aggiorna uno esistente.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 422de614d2e2ddb93cc1e932a8672e1e8269b2c0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636652"
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
[in] Puntatore a una definizione di classe valido. Deve essere inizializzata correttamente con tutti i valori proprietà obbligatorio.

`lFlags`\
[in] Una combinazione di flag che influiscono sul comportamento di questa funzione. I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se set, WMI non archivia i qualificatori con la versione modificata. <br> Se non impostato, si presuppone che non viene localizzato con questo oggetto e tutti i qualificatori vengono archiviati con questa istanza. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Creare la classe se non esiste o di sovrascriverlo se esiste già. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aggiornare la classe. La classe deve esistere per la chiamata abbia esito positivo. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Creare la classe. La chiamata ha esito negativo se la classe esiste già. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag determina una chiamata semisincrona. |
| `WBEM_FLAG_OWNER_UPDATE` | 0x10000 | Push provider devono specificare questo flag quando si chiama `PutClassWmi` per indicare che questa classe è stato modificato. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Consente a una classe da aggiornare se sono presenti nessuna classe derivata e nessuna istanza di tale classe. Consente inoltre aggiornamenti in tutti i casi se la modifica è qualificatori irrilevanti, ad esempio il qualificatore di descrizione. Se la classe dispone di istanze o le modifiche sono per qualificatori importanti, l'aggiornamento ha esito negativo. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | Consente gli aggiornamenti delle classi anche se sono presenti le classi figlio, purché la modifica non generi conflitti con le classi figlio. Ad esempio, questo flag consente una nuova proprietà da aggiungere alla classe di base che non è stata citata in precedenza in una qualsiasi delle classi figlio. Se la classe dispone di istanze, l'aggiornamento ha esito negativo. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | forza gli aggiornamenti delle classi quando sono presenti le classi figlio in conflitto. Ad esempio, questo flag impone un aggiornamento se un qualificatore di classe è definito in una classe figlio e la classe di base tenta di aggiungere lo stesso qualificatore che è in conflitto con quella esistente. In modalità di forza, tis conflitto viene risolto eliminando il qualificatore in conflitto nella classe figlio. |

`pCtx`\
[in] In genere, questo valore è `null`. In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istanza che può essere utilizzata dal provider che fornisce le classi richieste.

`ppCallResult`\
[out] Se `null`, questo parametro è inutilizzato. Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la funzione restituisce immediatamente il `WBEM_S_NO_ERROR`. Il `ppCallResult` parametro riceve un puntatore a una nuova [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) oggetto.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente dispone dell'autorizzazione per creare o modificare le classi. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La classe specificata non è valida. In genere, ciò indica che `pObject` specifica un oggetto istanza. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | Il nome della classe specificata non è valido. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | È stato effettuato un tentativo per apportare una modifica che avrebbe reso invalida una sottoclasse. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Il `WBEM_FLAG_CREATE_ONLY` flag è stato specificato, ma la classe esiste già. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` è stato specificato `lFlags`, la classe non è stata trovata. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | Le proprietà necessarie per le classi non di tutto configurate. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente arresto e riavvio. Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) (metodo).

L'utente non può creare classi con nomi che iniziano o terminano con un carattere di sottolineatura.

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** WMINet_Utils.idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
