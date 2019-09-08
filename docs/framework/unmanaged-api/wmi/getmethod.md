---
title: Funzione GetMethod (riferimenti alle API non gestite)
description: La funzione GetMethod recupera le informazioni su un metodo.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9cc185bf8cccb8ed3c24e28954afd86464602d7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798570"
---
# <a name="getmethod-function"></a>Funzione GetMethod

Recupera le informazioni relative al metodo specificato.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
in Nome del metodo. Questo parametro non può `null` essere e deve puntare a un `LPCWSTR`oggetto valido.

`lFlags`\
[in] Riservato. Questo parametro deve essere 0.

`ppInSignature`\
out Puntatore all'indirizzo di un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che descrive i parametri in per il metodo. Questo parametro viene ignorato se è impostato su `null`.

`ppOutSignature`\
out Puntatore all'indirizzo di un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che descrive i parametri out al metodo. Questo parametro viene ignorato se è impostato su `null`.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Impossibile trovare la proprietà specificata. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .

Gestione Windows può impostare il puntatore [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) su `null` se il metodo non dispone di parametri in.

In `ppInSignature` `IWbemClassObject` e `ppOutSignature` descrivono rispettivamente i parametri in e out come proprietà in un'istanza della classe di sistema [_Parameters](/windows/desktop/WmiSdk/--parameters). Le proprietà in `ppInSignature` sono denominate `Param` *n*, dove *n* è la posizione del parametro nella firma del metodo, ad `Param1`esempio `Param2`, e così via. Anche le proprietà `ppOutSignature` in sono denominate `Param` *n*e il valore restituito è `ReturnValue`denominato. Per ulteriori informazioni e un esempio, vedere [Metodo IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
