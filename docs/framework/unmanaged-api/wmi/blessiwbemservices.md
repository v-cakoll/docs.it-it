---
title: Funzione BlessIWbemServices (riferimenti alle API non gestite)
description: La funzione BlessIWbemServices indica se le credenziali utente consentono l'accesso a una classe IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a65c3c14507b2520c69875a1bc101ce826ace7ba
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934304"
---
# <a name="blessiwbemservices-function"></a>BlessIWbemServices (funzione)
Indica se le credenziali utente di consentono l'accesso all'oggetto specificato [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) classe.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>Parametri

`pIWbemServices`  
[in] Un puntatore per il [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto per cui sono necessarie le autorizzazioni.

`strUser`  
[in] Il nome utente.

`strPassword`  
[in] La password associata `strUser`.

`strAuthority` [in] Il nome di dominio dell'utente. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

`impLevel` [in] Il livello di rappresentazione.

`authnLevel` [in] Il livello di autorizzazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *Winerror* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o più argomenti non sono validi. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` è `null`. | 
| `E_FAIL` | 0x80000008 | Si è verificato un errore non specificato. |
| `E_OUTOFMEMORY` | 0x80000002 | Memoria disponibile è insufficiente per eseguire l'operazione. | 
| `S_OK` | 0 | La chiamata di funzione è riuscita. | 

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
