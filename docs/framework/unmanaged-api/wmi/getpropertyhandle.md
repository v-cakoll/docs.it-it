---
title: Funzione GetPropertyHandle (riferimenti alle API non gestite)
description: La funzione GetPropertyHandle restituisce un handle univoco che identifica una proprietà.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1397188b38066bac6375da0c76e7d66724a75d7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636248"
---
# <a name="getpropertyhandle-function"></a>Funzione GetPropertyHandle

Restituisce un handle univoco che identifica una proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro è inutilizzato.

`ptr`\
[in] Un puntatore a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) istanza.

`wszPropertyName`\
[in] Una terminazione null stringa di caratteri con codifica UTF16 che contiene il nome della proprietà.

`pType`\
[out] Un puntatore a un [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) membro di enumerazione che rappresenta il tipo CIM della proprietà.

`pHandle`\
[out] Un puntatore a un integer contenente l'handle di proprietà.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il nome della proprietà specificata non è stato trovato. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | La proprietà richiesta è di tipo vengono `CIM_OBJECT` o `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) (metodo).

È possibile usare questo handle per identificare le proprietà quando si usa [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) metodi per leggere o scrivere i valori delle proprietà.

Gli handle possono essere recuperati per le proprietà di tutti i tipi di dati diverso da `CIM_OBJECT` e `CIM_ARRAY`. Restituito lavoro handle per tutte le istanze di una classe.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** WMINet_Utils.idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
