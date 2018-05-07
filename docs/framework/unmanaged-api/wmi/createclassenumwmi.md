---
title: Funzione CreateClassEnumWmi (riferimenti alle API non gestite)
description: La funzione CreateClassEnumWmi restituisce un enumeratore per tutte le classi che soddisfano criteri specificati.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f84902586a2b940d52eb6365a141af61af802dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="createclassenumwmi-function"></a>CreateClassEnumWmi (funzione)
Restituisce un enumeratore per tutte le classi che soddisfano i criteri di selezione specificati.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

`strSuperclass`    
[in] Se non `null` o vuoto, che specifica il nome di una classe padre; l'enumeratore restituisce solo le sottoclassi di questa classe. Se è `null` o vuoto e `lFlags` WBEM_FLAG_SHALLOW, restituisce solo classi di primo livello (classi con nessuna classe padre). Se è `null` o vuoto e `lFlags` è `WBEM_FLAG_DEEP`, restituisce tutte le classi nello spazio dei nomi.

`lFlags`   
[in] Una combinazione di flag che influenzano il comportamento di questa funzione. I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice: 

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Se impostato, la funzione recupera i qualificatori archiviati nello spazio dei nomi localizzata delle impostazioni locali della connessione corrente. <br/> Se non impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato. |
| `WBEM_FLAG_DEEP` | 0 | L'enumerazione include tutte le sottoclassi nella gerarchia, ma non da questa classe. |
| `WBEM_FLAG_SHALLOW` | 1 | L'enumerazione include solo pure istanze di questa classe ed esclude tutte le istanze delle sottoclassi che forniscono le proprietà non è state trovate in questa classe. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Il flag determina una chiamata semisincrona. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | La funzione restituisce un enumeratore forward-only. In genere, gli enumeratori forward-only sono più veloci e utilizzano meno memoria convenzionali enumeratori, ma non consentono le chiamate a [Clone](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI consente di mantenere i puntatori agli oggetti di enumration finché vengono rilasciate. | 

I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per prestazioni ottimali.

`pCtx`  
[in] In genere, questo valore è `null`. In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) istanza che può essere utilizzato dal provider che fornisce le classi di richieste. 

`ppEnum`  
[out] Riceve il puntatore dell'enumeratore.

`authLevel`  
[in] Il livello di autorizzazione.

`impLevel` [in] Il livello di rappresentazione.

`pCurrentNamespace`   
[in] Un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto che rappresenta lo spazio dei nomi corrente.

`strUser`   
[in] Il nome utente. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

`strPassword`   
[in] La password. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

`strAuthority`   
[in] Il nome di dominio dell'utente. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | L'utente non dispone dell'autorizzazione per visualizzare uno o più classi che la funzione può restituire. |
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strSuperClass` non esiste. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI è stato probabilmente arrestato e riavviarlo. Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) metodo.

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
