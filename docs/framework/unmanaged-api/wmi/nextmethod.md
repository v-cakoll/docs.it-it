---
title: Funzione NextMethod (riferimenti alle API non gestite)
description: La funzione NextMethod recupera il metodo successivo nell'enumerazione.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9b14424bb914be3ba127670e1b6490f79854d6e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="nextmethod-function"></a>NextMethod (funzione)
Recupera un'enumerazione che inizia con una chiamata al metodo successivo [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
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
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pName`  
[out] Un puntatore che punta a `null` prima della chiamata. Quando la funzione restituisce, l'indirizzo di un nuovo `BSTR` che contiene il nome del metodo. 

`ppSignatureIn`  
[out] Un puntatore che riceve un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) che contiene il `in` parametri per il metodo. 

`ppSignatureOut`  
[out] Un puntatore che riceve un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) che contiene il `out` parametri per il metodo. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Si è verificato alcuna chiamata al [ `BeginEnumeration` ](beginenumeration.md) (funzione). |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non esistono altre proprietà nell'enumerazione. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) metodo.

Il chiamante ha inizio la sequenza di enumerazione chiamando il [BeginMethodEnumeration](beginmethodenumeration.md) funzione e quindi chiama la funzione [NextMethod] fino a quando la funzione restituisce `WBEM_S_NO_MORE_DATA`. Facoltativamente, il chiamante al termine della sequenza chiamando [EndMethodEnumeration](endmethodenumeration.md). Il chiamante può terminare in anticipo l'enumerazione chiamando [EndMethodEnumeration](endmethodenumeration.md) in qualsiasi momento.

## <a name="example"></a>Esempio

Per un esempio di C++, vedere il [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
