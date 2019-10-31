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
ms.openlocfilehash: 946d29892052ea69c2a8a3bf11e7be7a1b2d7068
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138773"
---
# <a name="blessiwbemservices-function"></a>Funzione BlessIWbemServices
Indica se le credenziali utente consentono l'accesso alla classe [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) specificata.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp
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

`pIWbemServices`\
in Puntatore all'oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) per il quale sono necessarie le autorizzazioni.

`strUser`\
in Nome utente.

`strPassword`\
in Password associata a `strUser`.

`strAuthority`\
in Nome di dominio dell'utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

`impLevel`\
in Livello di rappresentazione.

`authnLevel`\
in Livello di autorizzazione.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *Winerror. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o più argomenti non sono validi. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` è `null`. | 
| `E_FAIL` | 0x80000008 | Si è verificato un errore non specificato. |
| `E_OUTOFMEMORY` | 0x80000002 | Memoria insufficiente per eseguire l'operazione. | 
| `S_OK` | 0 | La chiamata di funzione è stata completata. | 

## <a name="requirements"></a>Requisiti  

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
