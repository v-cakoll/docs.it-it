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
ms.openlocfilehash: 67abf017040b9e6bbe9b10e560c8d57c124ae84e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743304"
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi (funzione)
Crea o aggiorna un'istanza di una classe esistente. L'istanza viene scritta nel repository WMI. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>Parametri

`pInst`    
[in] Un puntatore all'istanza di essere scritto.

`lFlags`   
[in] Una combinazione di flag che influiscono sul comportamento di questa funzione. I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice: 

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostato, WMI non archivia i qualificatori con il **modificato** flavor. </br> Se non impostato, si presuppone che non viene localizzato con questo oggetto e tutti i qualificatori vengono storedwith questa istanza. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Se non esiste o di sovrascriverlo se esiste già, creare l'istanza. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aggiornare l'istanza. L'istanza deve esistere per la chiamata abbia esito positivo. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Creare l'istanza. La chiamata ha esito negativo se l'istanza esiste già. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag determina una chiamata semisincrona. |

`pCtx`  
[in] In genere, questo valore è `null`. In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istanza che può essere utilizzata dal provider che fornisce le classi richieste. 

`ppCallResult`  
[out] Se `null`, questo parametro è inutilizzato. Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la funzione restituisce immediatamente il `WBEM_S_NO_ERROR`. Il `ppCallResult` parametro riceve un puntatore a una nuova [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) oggetto.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente dispone dell'autorizzazione per aggiornare un'istanza della classe specificata. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | La classe di supporto di questa istanza non è valida. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | un `null` è stato specificato per una proprietà che non può essere `null`, ad esempio un oggetto che è stata contrassegnata da un **Indexed** oppure **Not_Null** qualificatore. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | L'istanza specificata non è valido. (Ad esempio, la chiamata `PutInstanceWmi` con una classe restituisce questo valore.) |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Il `WBEM_FLAG_CREATE_ONLY` flag è stato specificato, ma l'istanza è già presente. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` è stato specificato `lFlags`, ma l'istanza non esiste. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente arresto e riavvio. Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) (metodo).

Il `PutInstanceWmi` funzione supporta la creazione di istanze e aggiornamento delle istanze di classi esistenti solo.  A seconda del modo in cui il `pCtx` parametro è impostato, alcune o tutte le proprietà dell'istanza vengono aggiornate. 

Quando l'istanza a cui punta `pInst` appartiene a una sottoclasse, gestione di Windows chiamate tutti i provider responsabile per le classi da cui deriva la sottoclasse. Tutti questi provider devono essere completate per originale `PutInstanceWmi` richiesta abbia esito positivo. Il provider che supporta la classe di livello superiore nella gerarchia viene chiamato per primo. Ordine di chiamata continua con la sottoclasse della classe di livello superiore e consente di passare dall'alto verso il basso finché gestione Windows raggiunge il provider per la classe proprietario di istanza a cui fa riferimento `pInst`.
Gestione di Windows non chiama il provider per tutte le classi figlio di un'istanza. 

Quando un'applicazione deve aggiornare un'istanza che appartiene a una gerarchia di classi, le `pInst` parametro deve puntare all'istanza che contiene le proprietà da modificare. Vale a dire, prendere in considerazione un'istanza di destinazione a cui appartiene **ClassB**. Il **ClassB** istanza derivata da **ClassA**, e **ClassA** definisce la proprietà **PropA**. Se un'applicazione vuole apportare una modifica al valore di **PropA** nel **ClassB** istanza, è necessario impostare `pInst` a quell'istanza anziché a un'istanza di **ClassA** .

La chiamata `PutInstanceWmi` in un'istanza di una classe astratta non è consentita.

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
