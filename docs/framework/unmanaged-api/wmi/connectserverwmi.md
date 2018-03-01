---
title: Funzione ConnectServerWmi (riferimenti alle API non gestite)
description: La funzione ConnectServerWmi utilizza DCOM per creare una connessione a uno spazio dei nomi WMI.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc821bddf1d33ea1144fef0821b81cf027d8f92f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi (funzione)
Crea una connessione mediante DCOM uno spazio dei nomi WMI in un computer specifico.  
  
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

`strNetworkResource`[in] Puntatore a un oggetto valido `BSTR` che contiene il percorso dell'oggetto dello spazio dei nomi WMI corretto. Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.

`strUser`[in] Un puntatore a un oggetto valido `BSTR` che contiene il nome utente. Oggetto `null` valore indica il contesto di sicurezza corrente. Se l'utente è di un dominio diverso da quello corrente, `strUser` può inoltre contenere il nome di dominio e separato da una barra rovesciata. `strUser`può anche essere utente nome principale (UPN) di formato, suhc come  *userName@domainName* . Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.

`strPassword`[in] Un puntatore a un oggetto valido `BSTR` che contiene la password. Oggetto `null` indica il contesto di sicurezza corrente. Una stringa vuota ("") indica una password valida di lunghezza zero.

`strLocale`[in] Un puntatore a un oggetto valido `BSTR` che indica le impostazioni locali corrette per il recupero di informazioni. Per gli identificatori delle impostazioni locali Microsoft, il formato della stringa è "MS\_*xxx*", dove *xxx* è una stringa in formato esadecimale che indica l'identificatore delle impostazioni locali (LCID). Se si specificano delle impostazioni locali non valida, il metodo restituisce `WBEM_E_INVALID_PARAMETER` tranne che in Windows 7, in cui le impostazioni locali predefinite del server viene utilizzata invece. Se ' viene utilizzato null1, le impostazioni locali correnti. 
 
`lSecurityFlags`[in] Flag da passare per il `ConnectServerWmi` metodo. Un valore pari a zero (0) per questo parametro determina la chiamata a `ConnectServerWmi` restituzione solo dopo che viene stabilita una connessione al server. Ciò potrebbe causare un'applicazione non risponde in modo indefinito se il server è interrotto. Gli altri valori validi sono:

| Costante  | Valore  | Descrizione  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Riservato per uso interno. Non usare. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi`Restituisce entro due minuti o meno. |

`strAuthority`[in] Il nome di dominio dell'utente. Se son presenti i seguenti valori:

| Valore | Descrizione |
|---------|---------|
| blank | Viene utilizzata l'autenticazione NTLM e viene utilizzato il dominio NTLM dell'utente corrente. Se `strUser` specifica il dominio (il percorso consigliato), non deve essere specificato qui. La funzione restituisce `WBEM_E_INVALID_PARAMETER` se si specifica il dominio in entrambi i parametri. |
| Kerberos:*nome dell'entità* | Viene utilizzata l'autenticazione Kerberos e questo parametro contiene un nome principale Kerberos. |
| NTLMDOMAIN:*nome di dominio* | Viene utilizzata l'autenticazione NT LAN Manager e questo parametro contiene un nome di dominio NTLM. |

`pCtx`   
[in] In genere, questo parametro è `null`. In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) oggetto richiesto da uno o più provider di classe dinamica. 

`ppNamespace`  
[out] Quando la funzione restituisce, riceve un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto associato allo spazio dei nomi specificato. Si è impostato per puntare alla `null` quando si verifica un errore.

`impLevel`  
[in] Il livello di rappresentazione.

`authLevel`  
[in] Il livello di autorizzazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) metodo.

 Per l'accesso locale per lo spazio dei nomi predefinito, `strNetworkResource` può essere un percorso dell'oggetto semplice: "root\default" o "\\.\root\default". Per l'accesso allo spazio dei nomi predefinito in un computer remoto con una rete compatibile con Microsoft o di COM, includere il nome del computer: "\\myserver\root\default". Inoltre, il nome del computer può essere un nome DNS o l'indirizzo IP. Il `ConnectServerWmi` (funzione) può inoltre connettersi con computer che eseguono IPv6 utilizzando un indirizzo IPv6.

`strUser`non può essere una stringa vuota. Se viene specificato il dominio `strAuthority`, non deve anche essere incluso `strUser`, o la funzione restituisce `WBEM_E_INVALID_PARAMETER`.


## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
