---
title: Funzione QualifierSet_BeginEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_BeginEnumeration Reimposta un enumeratore dei qualificatori di un oggetto.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b75c51ebddd78e447fed57b22a96c2d5c35004e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798341"
---
# <a name="qualifierset_beginenumeration-function"></a>QualifierSet_BeginEnumeration (funzione)

Reimposta un enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`\
in Combinazione bit per bit dei flag o valori descritti nella sezione [osservazioni](#remarks) che specifica i qualificatori da includere nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Il parametro `lFlags` non è valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `QualifierSet_BeginEnumeration` è stata effettuata senza una chiamata corrispondente a [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | La memoria disponibile non è sufficiente per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) .

Per enumerare tutti i qualificatori in un oggetto, questo metodo deve essere chiamato prima della prima chiamata a [QualifierSet_Next](qualifierset-next.md). L'ordine in cui vengono enumerati i qualificatori è sicuramente invariante per una determinata enumerazione.

I flag che possono essere passati come `lEnumFlags` argomento vengono definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|  | 0 | Restituisce i nomi di tutti i qualificatori. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituisce solo i nomi dei qualificatori specifici della proprietà o dell'oggetto corrente. <br/> Per una proprietà: Restituire solo i qualificatori specifici della proprietà (incluse le sostituzioni) e non i qualificatori propagati dalla definizione della classe. <br/> Per un'istanza: Restituisce solo nomi di qualificatori specifici dell'istanza. <br/> Per una classe: Restituisce solo i qualificatori specifici della classe derivata.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Restituisce solo i nomi dei qualificatori propagati da un altro oggetto. <br/> Per una proprietà: Restituisce solo i qualificatori propagati a questa proprietà dalla definizione della classe e non da quelli della proprietà stessa. <br/> Per un'istanza: Restituisce solo i qualificatori propagati dalla definizione della classe. <br/> Per una classe: Restituisce solo i nomi dei qualificatori ereditati dalle classi padre. |

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
