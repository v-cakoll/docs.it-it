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
ms.openlocfilehash: 57ab5eb418b5f0a9175074c87837c7cac8936346
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799054"
---
# <a name="blessiwbemservices-function"></a>Funzione BlessIWbemServices
Indica se le credenziali utente consentono l'accesso alla classe [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) specificata.   
  
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

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Uno o più argomenti non sono validi. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` è `null`. | 
| `E_FAIL` | 0x80000008 | Si è verificato un errore non specificato. |
| `E_OUTOFMEMORY` | 0x80000002 | Memoria insufficiente per eseguire l'operazione. | 
| `S_OK` | 0 | La chiamata di funzione è stata completata. | 

## <a name="requirements"></a>Requisiti  

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
