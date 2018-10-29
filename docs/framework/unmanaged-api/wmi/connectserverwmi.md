---
title: Funzione ConnectServerWmi (riferimenti alle API non gestite)
description: La funzione ConnectServerWmi Usa DCOM per creare una connessione a uno spazio dei nomi WMI.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa4b789641034b6563b15c52e96cbfdfa13d989a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197388"
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi (funzione)
Crea una connessione tramite DCOM a uno spazio dei nomi WMI in un computer specifico.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a>Parametri

`strNetworkResource` [in] Puntatore a un valore valido `BSTR` che contiene il percorso dell'oggetto dello spazio dei nomi WMI corretto. Vedere le [osservazioni](#remarks) sezione per altre informazioni.

`strUser` [in] Un puntatore a un valore valido `BSTR` che contiene il nome utente. Oggetto `null` valore indica il contesto di sicurezza corrente. Se l'utente è di un dominio diverso da quello corrente, `strUser` può inoltre contenere il nome utente e dominio separato da una barra rovesciata. `strUser` può anche essere nel formato user principal name (UPN), ad esempio `userName@domainName`. Vedere le [osservazioni](#remarks) sezione per altre informazioni.

`strPassword` [in] Un puntatore a un valore valido `BSTR` che contiene la password. Oggetto `null` indica il contesto di sicurezza corrente. Una stringa vuota ("") indica una password valida di lunghezza zero.

`strLocale` [in] Un puntatore a un valore valido `BSTR` che indica le impostazioni locali corrette per il recupero delle informazioni. Per gli identificatori delle impostazioni locali di Microsoft, il formato della stringa è "MS\_*xxx*", dove *xxx* è una stringa in formato esadecimale che indica l'identificatore delle impostazioni locali (LCID). Se si specifica delle impostazioni locali non valida, il metodo restituisce `WBEM_E_INVALID_PARAMETER` tranne che in Windows 7, in cui le impostazioni locali predefinite del server viene usata invece. Se ' viene usato null1, le impostazioni locali correnti. 
 
`lSecurityFlags` [in] Flag da passare per il `ConnectServerWmi` (metodo). Un valore pari a zero (0) per questo parametro determina la chiamata a `ConnectServerWmi` restituendo solo dopo aver stabilita una connessione al server. Ciò può comportare un'applicazione non risponde all'infinito se il server è interrotto. Gli altri valori validi sono:

| Costante  | Valore  | Descrizione  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Riservato per uso interno. Non usare. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi` Restituisce due minuti o meno. |

`strAuthority` [in] Il nome di dominio dell'utente. Se son presenti i seguenti valori:

| Valore | Descrizione |
|---------|---------|
| blank | Viene utilizzata l'autenticazione NTLM e viene utilizzato il dominio NTLM dell'utente corrente. Se `strUser` specifica il dominio (la posizione consigliata), non deve essere specificato qui. La funzione restituisce `WBEM_E_INVALID_PARAMETER` se si specifica il dominio in entrambi i parametri. |
| Kerberos:*nome dell'entità* | Viene utilizzata l'autenticazione Kerberos, e questo parametro contiene un nome dell'entità Kerberos. |
| NTLMDOMAIN:*nome di dominio* | Viene utilizzata l'autenticazione NT LAN Manager, e questo parametro contiene un nome di dominio NTLM. |

`pCtx`   
[in] In genere, questo parametro è `null`. In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) oggetto richiesto da uno o più provider di classe dinamica. 

`ppNamespace`  
[out] Quando termina, la funzione riceve un puntatore a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto associato allo spazio dei nomi specificato. Impostarlo in modo che punti a `null` quando si verifica un errore.

`impLevel`  
[in] Il livello di rappresentazione.

`authLevel`  
[in] Il livello di autorizzazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) (metodo).

 Per l'accesso locale per lo spazio dei nomi predefinito, `strNetworkResource` può essere un percorso semplice dell'oggetto: "root\default" o "\\.\root\default". Per l'accesso allo spazio dei nomi predefinito in un computer remoto utilizza COM o compatibile Microsoft, di rete, incluso il nome del computer: "\\myserver\root\default". Inoltre, il nome del computer può essere un nome DNS o indirizzo IP. Il `ConnectServerWmi` (funzione) possa anche connettersi con computer che eseguono IPv6 usando un indirizzo IPv6.

`strUser` non può essere una stringa vuota. Se il dominio specificato nel `strAuthority`, perché non deve inoltre essere incluso nella `strUser`, o la funzione restituisce `WBEM_E_INVALID_PARAMETER`.


## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
