---
title: Funzione ConnectServerWmi (riferimenti alle API non gestite)
description: La funzione ConnectServerWmi utilizza DCOM per creare una connessione a uno spazio dei nomi WMI.
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
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798746"
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi (funzione)

Crea una connessione tramite DCOM a uno spazio dei nomi WMI in un computer specifico.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
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

`strNetworkResource`\
in Puntatore a un oggetto `BSTR` valido che contiene il percorso dell'oggetto dello spazio dei nomi WMI corretto. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

`strUser`\
in Puntatore a un oggetto valido `BSTR` che contiene il nome utente. `null` Valore che indica il contesto di sicurezza corrente. Se l'utente si trova in un dominio diverso da quello corrente, `strUser` può contenere anche il dominio e il nome utente separati da una barra rovesciata. `strUser`può anche essere nel formato del nome dell'entità utente (UPN), `userName@domainName`ad esempio. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

`strPassword`\
in Puntatore a un oggetto valido `BSTR` che contiene la password. Indica `null` il contesto di sicurezza corrente. Una stringa vuota ("") indica una password di lunghezza zero valida.

`strLocale`\
in Puntatore a un oggetto valido `BSTR` che indica le impostazioni locali corrette per il recupero delle informazioni. Per gli identificatori delle impostazioni locali Microsoft, il formato della stringa è "\_MS*xxx*", dove *xxx* è una stringa in formato esadecimale che indica l'identificatore delle impostazioni locali (LCID). Se si specificano impostazioni locali non valide, il metodo `WBEM_E_INVALID_PARAMETER` restituisce eccetto Windows 7, in cui vengono invece usate le impostazioni locali predefinite del server. Se ' NULL1, vengono usate le impostazioni locali correnti.

`lSecurityFlags`\
in Flag da passare al `ConnectServerWmi` metodo. Il valore zero (0) per questo parametro determina la `ConnectServerWmi` restituzione della chiamata solo dopo che è stata stabilita una connessione al server. Questo potrebbe comportare un'applicazione che non risponde a tempo indefinito se il server è danneggiato. Gli altri valori validi sono:

| Costante  | Value  | DESCRIZIONE  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | Riservato per uso interno. Non usare. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi`Restituisce tra due minuti o meno. |

`strAuthority`\
in Nome di dominio dell'utente. Se son presenti i seguenti valori:

| Value | Descrizione |
|---------|---------|
| blank | Viene utilizzata l'autenticazione NTLM e viene utilizzato il dominio NTLM dell'utente corrente. Se `strUser` specifica il dominio (percorso consigliato), non deve essere specificato qui. La funzione restituisce `WBEM_E_INVALID_PARAMETER` se si specifica il dominio in entrambi i parametri. |
| Kerberos:*nome entità* | Viene utilizzata l'autenticazione Kerberos e questo parametro contiene il nome di un'entità Kerberos. |
| NTLMDOMAIN:*nome di dominio* | Viene utilizzata l'autenticazione NT LAN Manager e questo parametro contiene un nome di dominio NTLM. |

`pCtx`\
in In genere, questo parametro `null`è. In caso contrario, è un puntatore a un oggetto [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) richiesto da uno o più provider di classi dinamici.

`ppNamespace`\
out Quando la funzione restituisce un risultato, riceve un puntatore a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) associato allo spazio dei nomi specificato. Viene impostato in modo da puntare `null` a quando si verifica un errore.

`impLevel`\
in Livello di rappresentazione.

`authLevel`\
in Livello di autorizzazione.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) .

Per l'accesso locale allo spazio dei nomi `strNetworkResource` predefinito, può essere un percorso di oggetto semplice: "root\default\\" o ".\root\default". Per accedere allo spazio dei nomi predefinito in un computer remoto utilizzando le reti com o compatibili con Microsoft, includere il nome del\\computer: "myserver\root\default". Il nome del computer può anche essere un nome DNS o un indirizzo IP. La `ConnectServerWmi` funzione può inoltre connettersi a computer che eseguono IPv6 utilizzando un indirizzo IPv6.

`strUser`non può essere una stringa vuota. Se il dominio viene specificato in `strAuthority`, non deve essere incluso anche in `strUser`oppure la funzione restituisce `WBEM_E_INVALID_PARAMETER`.

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils. idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
