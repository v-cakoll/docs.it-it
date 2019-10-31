---
title: Funzione QualifierSet_GetNames (riferimenti alle API non gestite)
description: La funzione QualifierSet_GetNames recupera i nomi dei qualificatori da un oggetto o da una proprietà.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141699"
---
# <a name="qualifierset_getnames-function"></a>QualifierSet_GetNames (funzione)

Recupera i nomi di tutti i qualificatori o di determinati qualificatori disponibili dall'oggetto o dalla proprietà corrente.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`\
in Uno dei seguenti flag o valori che specifica i nomi da includere nell'enumerazione.

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|  | 0 | Restituisce i nomi di tutti i qualificatori. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituisce solo i nomi dei qualificatori specifici della proprietà o dell'oggetto corrente. <br/> Per una proprietà: restituire solo i qualificatori specifici della proprietà (incluse le sostituzioni) e non i qualificatori propagati dalla definizione della classe. <br/> Per un'istanza: restituire solo nomi di qualificatori specifici dell'istanza. <br/> Per una classe: restituire solo i qualificatori specifici della classe derivata.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Restituisce solo i nomi dei qualificatori propagati da un altro oggetto. <br/> Per una proprietà: restituire solo i qualificatori propagati a questa proprietà dalla definizione della classe e non da quelli della proprietà stessa. <br/> Per un'istanza: restituire solo i qualificatori propagati dalla definizione della classe. <br/> Per una classe: restituire solo i nomi dei qualificatori ereditati dalle classi padre. |

`pstrNames`\
out Nuovo `SAFEARRAY` contenente i nomi richiesti. La matrice può avere 0 elementi. Se si verifica un errore, non viene restituito un nuovo `SAFEARRAY`.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | La memoria disponibile non è sufficiente per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .

Una volta recuperati i nomi dei qualificatori, è possibile accedere a ogni qualificatore in base al nome chiamando la funzione [QualifierSet_Get](qualifierset-get.md) .

Non si tratta di un errore per un dato oggetto con qualificatori zero, quindi il numero di stringhe nel `pstrNames` restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
