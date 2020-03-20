---
title: BeginEnumeration function (Unmanaged API Reference)
description: La funzione BeginEnumeration reimposta un enumeratore all'inizio dell'enumerazione
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176877"
---
# <a name="beginenumeration-function"></a>Funzione BeginEnumeration
Reimposta un enumeratore all'inizio dell'enumerazione.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro non viene utilizzato.

`ptr`\
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lEnumFlags`\
[in] Combinazione bit per bit dei flag o dei valori descritti nella sezione [Osservazioni](#remarks) che controlla le proprietà incluse nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinazione di `lEnumFlags` flag in non è valida o è stato specificato un argomento non valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda `BeginEnumeration` chiamata è stata fatta [`EndEnumeration`](endenumeration.md)senza una chiamata intermedia a . |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

I flag che possono `lEnumFlags` essere passati come argomento sono definiti nel file di intestazione *WbemCli.h* oppure è possibile definirli come costanti nel codice.  È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo. Tuttavia, i flag dello stesso gruppo si escludono a vicenda.

**Gruppo 1**

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Includere solo le proprietà che costituiscono la chiave. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Includere solo le proprietà che sono riferimenti a oggetti. |

**Gruppo 2**

Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 (in modo 0x30) | Limitare l'enumerazione solo alle proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Includere le proprietà locali e propagate ma escludere le proprietà di sistema dall'enumerazione. |

Per le classi:

Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limitare l'enumerazione alle proprietà sottoposte a override nella definizione della classe. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limitare l'enumerazione alle proprietà sottoposte a override nella definizione di classe corrente e alle nuove proprietà definite nella classe. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 (in 300) | Maschera (anziché un flag) da `lEnumFlags` applicare a `WBEM_FLAG_CLASS_OVERRIDES_ONLY` un `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` valore per verificare se è o è impostato. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione alle proprietà ereditate dalle classi base. |

Per le istanze:

Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione alle proprietà ereditate dalle classi base. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
