---
title: Funzione BeginEnumeration (riferimenti alle API non gestite)
description: La funzione BeginEnumeration Reimposta l'enumeratore all'inizio dell'enumerazione
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90c3e8448a61145290ea4a75b1d38f7ae010cb9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a>BeginEnumeration (funzione)
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

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lEnumFlags`  
[in] Combinazione bit per bit dei valori descritti in o flag di [osservazioni](#remarks) sezione che controlla le proprietà incluse nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | La combinazione di flag in `lEnumFlags` non è valido o non valido è stato specificato l'argomento. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `BeginEnumeration` è stato eseguito senza una corrispondente chiamata a [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per avviare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) metodo.

I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.  È possibile combinare un flag di ogni gruppo con un flag da qualsiasi altro gruppo. Tuttavia, i flag dello stesso gruppo si escludono a vicenda. 

**Gruppo 1**

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Includono le proprietà che costituiscono la chiave solo. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Le proprietà solo i riferimenti agli oggetti. |

**Gruppo 2**

Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Limitare l'enumerazione solo le proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Include le proprietà locali e propagate ma esclude le proprietà di sistema dall'enumerazione. |

Per le classi:

Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Limitare la proprietà viene sottoposto a override nella definizione della classe dell'enumerazione. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Limitare l'enumerazione per proprietà sottoposto a override in una definizione di classe corrente e per le nuove proprietà definita nella classe. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Una maschera (anziché un flag) da applicare rispetto una `lEnumFlags` valore da controllare se il valore `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` è impostata. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare la proprietà che vengono definite o modificate nella stessa classe dell'enumerazione. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione di proprietà ereditate dalle classi di base. |

Per le istanze:

Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare la proprietà che vengono definite o modificate nella stessa classe dell'enumerazione. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione di proprietà ereditate dalle classi di base. |


## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
