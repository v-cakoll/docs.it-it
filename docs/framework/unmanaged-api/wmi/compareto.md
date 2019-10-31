---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo confronta un oggetto con un altro oggetto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128703"
---
# <a name="compareto-function"></a>Funzione CompareTo

Confronta un oggetto con un altro oggetto di Gestione Windows.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`flags`\
in Combinazione bit per bit dei flag che specificano le caratteristiche dell'oggetto da considerare per il confronto. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

`pCompareTo`\
in Oggetto per il confronto. `pCompareTo` deve essere un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) valida; non può essere `null`.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `BeginEnumeration` è stata effettuata senza una chiamata corrispondente a [`EndEnumeration`](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Gli oggetti sono diversi. |
| `WBEM_S_SAME` | 0 | Gli oggetti sono gli stessi in base ai flag di confronto. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) .

I flag che possono essere passati come `lEnumFlags` argomento vengono definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice. È possibile specificare le singole caratteristiche necessarie per il confronto specificando una combinazione bit per bit dei flag seguenti:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Ignorare l'origine (il server e lo spazio dei nomi da cui provengono). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Ignora tutti i qualificatori (incluse la **chiave** e la **dinamica**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Ignorare i valori predefiniti delle proprietà. Questo flag è valido solo per il confronto delle classi. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Ignora le versioni del qualificatore. Questo flag prende ancora in considerazione i qualificatori, ma ignora le distinzioni di sapore, ad esempio le regole di propagazione e le restrizioni di sostituzione. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Ignora case per il confronto di valori stringa. Questo vale sia per le stringhe che per i valori del qualificatore. Il confronto dei nomi di proprietà e qualificatore è sempre distinzione tra maiuscole e minuscole, indipendentemente dal fatto che questo flag sia impostato. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Si supponga che gli oggetti da confrontare siano istanze della stessa classe. Di conseguenza, questo flag confronta solo le informazioni correlate all'istanza. Usare questi flag per ottimizzare le prestazioni. Se gli oggetti non sono della stessa classe, i risultati non sono definiti. |

In alternativa, è possibile specificare un singolo flag composito come indicato di seguito:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Prendere in considerazione tutte le funzionalità del confronto. |

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
