---
title: Funzione GetPropertyOrigin (riferimenti alle API non gestite)
description: La funzione GetPropertyOrigin determina la classe in cui viene dichiarata una proprietà.
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6cab3765f0359f5dd18831acaaa1aefce3fe1081
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101856"
---
# <a name="getpropertyorigin-function"></a>Funzione GetPropertyOrigin

Determina la classe in cui viene dichiarata una proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszMethodName`\
in Nome della proprietà per l'oggetto di cui viene richiesta la classe proprietaria.

`pstrClassName`\
out Riceve il nome della classe a cui appartiene la proprietà.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Impossibile trovare la proprietà specificata. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) .

Poiché una classe può ereditare proprietà da una o più classi di base, gli sviluppatori spesso vogliono determinare la proprietà in cui è definito un determinato metodo.

Il parametro `pstrClassName` non deve puntare a una `BSTR` valida prima della chiamata della funzione perché si tratta di un parametro `out`; Questo puntatore non viene deallocato dopo la restituzione della funzione.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
