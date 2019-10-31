---
title: Funzione QualifierSet_Put (riferimenti alle API non gestite)
description: La funzione QualifierSet_Put scrive il qualificatore denominato e il relativo valore.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120239"
---
# <a name="qualifierset_put-function"></a>QualifierSet_Put (funzione)

Scrive il qualificatore e il valore denominati. Il nuovo qualificatore sovrascrive il valore precedente con lo stesso nome. Se il qualificatore non esiste, viene creato.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName`\
in Nome del qualificatore da scrivere.

`pVal`\
in Puntatore a un `VARIANT` valido che contiene il qualificatore da scrivere. Questo parametro non può essere `null`.

`lFlavor`\
in Una delle costanti seguenti che definisce le versioni del qualificatore desiderate per questo qualificatore. Il valore predefinito è `WBEM_FLAVOR_OVERRIDABLE` (0).

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Il qualificatore può essere sottoposto a override in una classe o un'istanza derivata. **Si tratta del valore predefinito.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Il qualificatore viene propagato alle istanze. |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Il qualificatore viene propagato alle classi derivate. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | Il qualificatore non può essere sottoposto a override in una classe o in un'istanza derivata. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | Il qualificatore è localizzato. |

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Si è verificato un tentativo non valido di specificare il qualificatore di **chiave** su una proprietà che non può essere una chiave. Le chiavi sono specificate nella definizione della classe per un oggetto e non possono essere modificate per ogni singola istanza. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | Il parametro `pVal` non è di un tipo di qualificatore valido. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Non è possibile chiamare il metodo `QualifierSet_Put` sul qualificatore perché l'oggetto proprietario non consente le sostituzioni. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) .

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
