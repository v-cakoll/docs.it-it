---
title: Funzione QualifierSet_BeginEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_BeginEnumeration Reimposta l'enumeratore dei qualificatori di un oggetto.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 440dde03f4ed138a33eb6f817723d7c5c74f6d46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetbeginenumeration-function"></a>QualifierSet_BeginEnumeration (funzione)
Reimposta l'enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`   
[in] Questo parametro è inutilizzato.

`ptr`   
[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.

`lFlags`   
[in] Combinazione bit per bit dei valori descritti in o flag di [osservazioni](#remarks) sezione che specifica i qualificatori da includere nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Il `lFlags` parametro non è valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `QualifierSet_BeginEnumeration` è stato eseguito senza una corrispondente chiamata a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per avviare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) metodo.

Per enumerare tutti i qualificatori su un oggetto, questo metodo deve essere chiamato prima della prima chiamata a [QualifierSet_Next](qualifierset-next.md). L'ordine in cui vengono enumerati i qualificatori è invariante per un'enumerazione specificata.

I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.   

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|  | 0 | Restituisce i nomi di tutti i qualificatori. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto. <br/> Per una proprietà: restituire solo i qualificatori specifici per la proprietà (inclusi sostituzioni) e non i qualificatori propagate dalla definizione della classe. <br/> Ad esempio: restituire solo i nomi di qualificatore specifici dell'istanza. <br/> Per una classe: restituire solo i qualificatori specifico beiong la classe derivata.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Restituire solo i nomi dei qualificatori propagati da un altro oggetto. <br/> Per una proprietà: restituiscono solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli di proprietà stessa. <br/> Ad esempio: restituzione solo tali qualificatori propagati dalla definizione della classe. <br/> Per una classe: restituiscono solo i nomi di qualificatore ereditati dalle classi padre. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
