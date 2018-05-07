---
title: Funzione WritePropertyValue (riferimenti alle API non gestite)
description: La funzione di WritePropertyValue scrive byte in una proprietà.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6aafb918616d27cf6289a8747f3336b2e813beb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue (funzione)
Scrive un numero specificato di byte a una proprietà identificata da un handle di proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) istanza.

`lHandle`  
[in] Valore intero che contiene l'handle che identifica questa proprietà. L'handle può essere recuperato chiamando il [GetPropertyHandle](getpropertyhandle.md) (funzione).   

`lNumBytes`  
[in] Il numero di byte da scrivere per la proprietà. Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.

`pHandle`   
[out] Puntatore alla matrice di byte che contiene i dati.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Si è verificato un tipo non corrispondente. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) metodo.

Utilizzare questa funzione per impostare una stringa e tutti gli altri non -`DWORD` o non-`QWORD` dati.

Per i valori delle proprietà non stringa `lNumBytes` deve corrispondere alla dimensione di correggere i dati del tipo di proprietà specificato. Per i valori di proprietà stringa `lNumBytes` devono avere la lunghezza della stringa specificata in byte con la stringa deve essere di pari lunghezza in byte ed essere seguita da un carattere di terminazione null.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
