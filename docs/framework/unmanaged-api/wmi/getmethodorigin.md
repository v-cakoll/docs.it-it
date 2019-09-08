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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cea7251353dae093f64448c8d84157917fa74c5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798553"
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
in Questo parametro è inutilizzato.

`ptr`  
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszMethodName`  
in Nome del metodo per l'oggetto di cui viene richiesta la classe proprietaria. 

`pstrClassName`  
out Riceve il nome della classe a cui appartiene il metodo.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |DESCRIZIONE  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non è stato trovato. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .

Poiché una classe può ereditare metodi da una o più classi base, gli sviluppatori spesso vogliono determinare la classe in cui è definito un determinato metodo.

Il `pstrClassName` parametro non deve puntare a un oggetto `BSTR` valido prima che la funzione venga chiamata perché si `out` tratta di un parametro; questo puntatore non viene deallocato dopo la restituzione della funzione.

## <a name="requirements"></a>Requisiti  
**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
