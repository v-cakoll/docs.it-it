---
title: Funzione BeginEnumeration (riferimenti alle API non gestite)
description: La funzione BeginEnumeration Reimposta un enumeratore all'inizio dell'enumerazione.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de36650aa2b206b5e9734b38c6067a3a79de610c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798789"
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
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lEnumFlags`\
in Combinazione bit per bit dei flag o dei valori descritti nella sezione [osservazioni](#remarks) che controlla le proprietà incluse nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinazione di flag in `lEnumFlags` non è valida oppure è stato specificato un argomento non valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `BeginEnumeration` è stata effettuata senza una chiamata corrispondente a [`EndEnumeration`](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | La memoria disponibile non è sufficiente per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

I flag che possono essere passati come `lEnumFlags` argomento vengono definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.  È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo. Tuttavia, i flag dello stesso gruppo si escludono a vicenda. 

**Gruppo 1**

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Includere le proprietà che costituiscono solo la chiave. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Includere proprietà che sono solo riferimenti a oggetti. |

**Gruppo 2**

Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Limitare l'enumerazione solo alle proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Includere proprietà locali e propagate, escluse le proprietà di sistema dall'enumerazione. |

Per le classi:

Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limitare l'enumerazione alle proprietà sottoposte a override nella definizione della classe. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limitare l'enumerazione alle proprietà sottoposte a override nella definizione della classe corrente e alle nuove proprietà definite nella classe. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Maschera (anziché un flag) da applicare a un `lEnumFlags` valore per verificare `WBEM_FLAG_CLASS_OVERRIDES_ONLY` se è impostato o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` . |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione alle proprietà ereditate dalle classi di base. |

Per le istanze:

Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione alle proprietà ereditate dalle classi di base. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
