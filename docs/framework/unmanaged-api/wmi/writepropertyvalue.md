---
title: WritePropertyValue function (Unmanaged API Reference)
description: La funzione WritePropertyValue scrive byte in una proprietà.
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174836"
---
# <a name="writepropertyvalue-function"></a>Funzione WritePropertyValue
Scrive un numero specificato di byte in una proprietà identificata da un handle di proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi  
  
```cpp  
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
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a un'istanza di [IWbemObjectAccess.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)

`lHandle`  
[in] Intero che contiene l'handle che identifica questa proprietà. L'handle può essere recuperato chiamando il [GetPropertyHandle](getpropertyhandle.md) funzione.

`lNumBytes`  
[in] Numero di byte scritti nella proprietà. Vedere la sezione [Osservazioni](#remarks) per ulteriori informazioni.

`pHandle`[fuori] Puntatore alla matrice di byte che contiene i dati.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Si è verificata un'incongruenza di tipo. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .

Utilizzare questa funzione per impostare`DWORD` la stringa`QWORD` e tutti gli altri dati non o non.

Per i valori `lNumBytes` di proprietà non stringa, deve essere la dimensione dei dati corretta del tipo di proprietà specificato. Per i valori `lNumBytes` di proprietà stringa, deve essere la lunghezza della stringa specificata in byte e la stringa stessa deve essere di lunghezza pari in byte ed essere seguita con un carattere di terminazione null.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
