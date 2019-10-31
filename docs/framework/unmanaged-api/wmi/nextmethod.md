---
title: Funzione NextMethod (riferimenti alle API non gestite)
description: La funzione NextMethod Recupera il metodo successivo in un'enumerazione.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127366"
---
# <a name="nextmethod-function"></a>NextMethod (funzione)
Recupera il metodo successivo in un'enumerazione che inizia con una chiamata a [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
in Questo parametro è inutilizzato.

`ptr`  
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pName`  
out Puntatore che punta a `null` prima della chiamata. Quando la funzione restituisce, l'indirizzo di un nuovo `BSTR` che contiene il nome del metodo. 

`ppSignatureIn`  
out Puntatore che riceve un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i parametri di `in` per il metodo. 

`ppSignatureOut`  
out Puntatore che riceve un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i parametri di `out` per il metodo. 

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Non è stata chiamata la funzione [`BeginEnumeration`](beginenumeration.md) . |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non sono presenti altre proprietà nell'enumerazione. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

Il chiamante avvia la sequenza di enumerazione chiamando la funzione [BeginMethodEnumeration](beginmethodenumeration.md) e quindi chiama la funzione [NextMethod] finché la funzione non restituisce `WBEM_S_NO_MORE_DATA`. Facoltativamente, il chiamante completa la sequenza chiamando [EndMethodEnumeration](endmethodenumeration.md). Il chiamante può terminare l'enumerazione prima chiamando [EndMethodEnumeration](endmethodenumeration.md) in qualsiasi momento.

## <a name="example"></a>Esempio

Per un C++ esempio, vedere il metodo [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
