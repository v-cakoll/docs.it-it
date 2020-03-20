---
title: Funzione GetMethodOrigin (riferimenti alle API non gestite)
description: La funzione GetMethodOrigin determina la classe in cui viene dichiarato un metodo.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b4609b6649be875aea7dfcf52ba36b1e98ab7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176799"
---
# <a name="getmethodorigin-function"></a>Funzione GetMethodOrigin
Determina la classe in cui viene dichiarato un metodo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszMethodName`  
[in] Nome del metodo per l'oggetto di cui viene richiesta la classe proprietaria.

`pstrClassName`  
[fuori] Riceve il nome della classe proprietaria del metodo.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non è stato trovato. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .

Poiché una classe può ereditare metodi da una o più classi base, gli sviluppatori spesso desiderano determinare la classe in cui è definito un determinato metodo.

Il `pstrClassName` parametro non deve `BSTR` puntare a un valido `out` prima che la funzione viene chiamata perché si tratta di un parametro. questo puntatore non viene deallocato dopo la restituzione della funzione.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
