---
title: Funzione QualifierSet_Put (riferimenti alle API non gestite)
description: La funzione QualifierSet_Put scrive qualificatore denominato e il relativo valore.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bf5c6dbf0f707942d58f4d7cf155636f0532724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetput-function"></a>QualifierSet_Put (funzione)
Scrive il qualificatore denominato e il valore. Nuovo qualificatore sovrascrive il valore precedente con lo stesso nome. Se il qualificatore non esiste, viene creato. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`   
[in] Questo parametro è inutilizzato.

`ptr`   
[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.

`wszName`   
[in] Il nome del qualificatore da scrivere.

`pVal`[in] Un puntatore a un oggetto valido `VARIANT` che contiene il qualificatore da scrivere. Questo parametro non può essere `null`.

`lFlavor`[in] Una delle costanti seguenti che definisce i tipi di qualificatore desiderato per il qualificatore. Il valore predefinito è `WBEM_FLAVOR_OVERRIDABLE` (0).

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Il qualificatore può essere sottoposto a override in una classe derivata o istanza. **Questo è il valore predefinito.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Il qualificatore viene propagato alle istanze. |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Il qualificatore viene propagato alle classi derivate. |
| ' WBEM_FLAVOR_NOT_OVERRIDABLE | 0x10 | Il qualificatore non può essere sottoposto a override in una classe o in un'istanza derivata. |
| ' WBEM_FLAVOR_AMENDED | 0x80 | Il qualificatore è localizzato. |

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Si è verificato un tentativo non valido per specificare il **chiave** qualificatore su una proprietà che non può essere una chiave. Le chiavi sono specificate om c; definizione ass per un oggetto e non possono essere alterate per ogni istanza. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | Il `pVal` parametro non è di un tipo di qualificatore valido. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Non è possibile chiamare il `QualifierSet_Put` metodo sul qualificatore perché l'oggetto proprietario non consente sostituzioni. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
