---
title: Funzione BeginEnumeration (riferimenti alle API non gestite)
description: La funzione di BeginEnumeration Reimposta l'enumeratore all'inizio dell'enumerazione
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
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212297"
---
# <a name="beginenumeration-function"></a>Funzione BeginEnumeration
Reimposta l'enumeratore all'inizio dell'enumerazione.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro è inutilizzato.

`ptr`\
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`lEnumFlags`\
[in] Una combinazione bit per bit del flag o i valori descritti nel [osservazioni](#remarks) sezione che controlla le proprietà incluse nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinazione di flag in `lEnumFlags` non è valido o non valido è stato specificato l'argomento. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) (metodo).

I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.  È possibile combinare un flag di ogni gruppo con eventuali flag da qualsiasi altro gruppo. Tuttavia, i flag dallo stesso gruppo si escludono a vicenda. 

**Gruppo 1**

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Include le proprietà che costituiscono solo la chiave. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Include le proprietà che sono solo i riferimenti agli oggetti. |

**Gruppo 2**

Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Limitare l'enumerazione per solo le proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Include le proprietà locali e propagate ma ne esclude le proprietà di sistema dall'enumerazione. |

Per le classi:

Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limitare la proprietà viene sottoposto a override nella definizione della classe dell'enumerazione. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limitare l'enumerazione alle proprietà sottoposto a override nella definizione della classe corrente e alle nuove proprietà definite nella classe. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Una maschera (invece di un flag) da applicare rispetto un' `lEnumFlags` valore per verificare se uno dei due `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` è impostata. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione alle proprietà definite o modificato nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione delle proprietà ereditate dalle classi di base. |

Per le istanze:

Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione alle proprietà definite o modificato nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione delle proprietà ereditate dalle classi di base. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)