---
title: Funzione QualifierSet_Put (riferimenti alle API non gestite)
description: La funzione QualifierSet_Put scrive qualificatore denominato e il relativo valore.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e42cf3440bef030f5c7bec71ed1b4b875b79a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000272"
---
# <a name="qualifiersetput-function"></a>QualifierSet_Put (funzione)

Scrive il qualificatore e il valore denominati. Nuovo qualificatore sovrascrive il valore precedente con lo stesso nome. Se il qualificatore non esiste, viene creato.

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
[in] Questo parametro è inutilizzato.

`ptr`\
[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.

`wszName`\
[in] Il nome del qualificatore da scrivere.

`pVal`\
[in] Un puntatore a un valore valido `VARIANT` che contiene il qualificatore da scrivere. Questo parametro non può essere `null`.

`lFlavor`\
[in] Una delle costanti seguenti che definisce il contrassegno qualificatore desiderato per questo qualificatore. Il valore predefinito è `WBEM_FLAVOR_OVERRIDABLE` (0).

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Il qualificatore può essere sottoposto a override in un'istanza o una classe derivata. **Questo è il valore predefinito.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Il qualificatore viene propagato alle istanze. |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Il qualificatore viene propagato alle classi derivate. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | Il qualificatore non può essere sottoposto a override in una classe o in un'istanza derivata. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | Il qualificatore è localizzato. |

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Si è verificato un tentativo non valido per specificare il **chiave** qualificatore su una proprietà che non può essere una chiave. Le chiavi specificate del modello a oggetti c; definizione di set di disponibilità per un oggetto e non può essere modificato in ogni istanza. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | Il `pVal` parametro non è di un tipo di qualificatore valido. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Non è possibile chiamare il `QualifierSet_Put` metodo sul qualificatore poiché l'oggetto proprietario non consente sostituzioni. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) (metodo).

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** WMINet_Utils.idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)