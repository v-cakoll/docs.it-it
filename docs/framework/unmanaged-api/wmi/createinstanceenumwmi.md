---
title: Funzione CreateInstanceEnumWmi (riferimenti alle API non gestite)
description: La funzione CreateInstanceEnumWmi restituisce un enumeratore contenente le istanze di una classe specificata che soddisfano i criteri di selezione.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7709d9c50a494013ece2f91b3acc213278f0e57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798911"
---
# <a name="createinstanceenumwmi-function"></a>CreateInstanceEnumWmi (funzione)

Restituisce un enumeratore che restituisce le istanze di una classe specificata che soddisfa i criteri di selezione specificati.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
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

`strFilter`\
in Nome della classe per cui si desiderano le istanze. Questo parametro non può `null`essere.

`lFlags`\
in Combinazione di flag che influiscono sul comportamento di questa funzione. I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostata, la funzione recupera i qualificatori modificati archiviati nello spazio dei nomi localizzato delle impostazioni locali della connessione corrente. <br/> Se non è impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato. |
| `WBEM_FLAG_DEEP` | 0 | L'enumerazione include questa e tutte le sottoclassi nella gerarchia. |
| `WBEM_FLAG_SHALLOW` | 1 | L'enumerazione include solo le istanze pure di questa classe ed esclude tutte le istanze delle sottoclassi che forniscono proprietà non trovate in questa classe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag causa una chiamata semisincrono. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La funzione restituisce un enumeratore di sola trasmissione. In genere, gli enumeratori di sola trasmissione sono più veloci e utilizzano meno memoria rispetto agli enumeratori convenzionali, ma non consentono le chiamate da [clonare](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI mantiene i puntatori agli oggetti nell'enumerazione fino a quando non vengono rilasciati. |

I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per ottenere prestazioni ottimali.

`pCtx`\
in In genere, questo valore `null`è. In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le istanze richieste.

`ppEnum`\
out Riceve il puntatore all'enumeratore.

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

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone delle autorizzazioni necessarie per visualizzare le istanze della classe specificata. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strFilter` non esiste. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente interrotto e riavviato. Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) . |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) .

Si noti che l'enumeratore restituito può avere zero elementi.

Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
