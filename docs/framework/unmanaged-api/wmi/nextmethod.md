---
title: NextMethod (riferimento alle API non gestite)
description: La funzione NextMethod recupera il metodo successivo in un'enumerazione.
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
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174927"
---
# <a name="nextmethod-function"></a>Funzione NextMethod
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
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pName`  
[fuori] Puntatore a `null` cui punta prima della chiamata. Quando la funzione restituisce, `BSTR` l'indirizzo di un nuovo che contiene il nome del metodo.

`ppSignatureIn`  
[fuori] Puntatore che riceve un puntatore a un oggetto `in` [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i parametri per il metodo.

`ppSignatureOut`  
[fuori] Puntatore che riceve un puntatore a un oggetto `out` [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i parametri per il metodo.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Non è stata [`BeginEnumeration`](beginenumeration.md) chiamata alla funzione. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non sono presenti altre proprietà nell'enumerazione. |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

Il chiamante inizia la sequenza di enumerazione chiamando la funzione [BeginMethodEnumeration](beginmethodenumeration.md) `WBEM_S_NO_MORE_DATA`, quindi chiama la funzione [NextMethod] finché la funzione non restituisce . Facoltativamente, il chiamante completa la sequenza chiamando [EndMethodEnumeration](endmethodenumeration.md). Il chiamante può terminare l'enumerazione in anticipo chiamando [EndMethodEnumeration](endmethodenumeration.md) in qualsiasi momento.

## <a name="example"></a>Esempio

Per un esempio in C, vedere il metodo [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
