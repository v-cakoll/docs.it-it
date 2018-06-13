---
title: Funzione QualifierSet_GetNames (riferimenti alle API non gestite)
description: La funzione QualifierSet_GetNames recupera i nomi dei qualificatori da un oggetto o una proprietà.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7c96439cf50c18e336baa70cf463b9463203290
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461178"
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames (funzione)
Recupera i nomi di tutti i qualificatori o di alcuni qualificatori disponibili dall'oggetto corrente o dalla proprietà. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`   
[in] Questo parametro è inutilizzato.

`ptr`   
[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.

`lFlags`   
[in] Uno dei flag seguenti o valori che specifica i nomi da includere nell'enumerazione.

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|  | 0 | Restituisce i nomi di tutti i qualificatori. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto. <br/> Per una proprietà: restituire solo i qualificatori specifici per la proprietà (inclusi sostituzioni) e non i qualificatori propagate dalla definizione della classe. <br/> Ad esempio: restituire solo i nomi di qualificatore specifici dell'istanza. <br/> Per una classe: restituire solo i qualificatori specifico beiong la classe derivata.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Restituire solo i nomi dei qualificatori propagati da un altro oggetto. <br/> Per una proprietà: restituiscono solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli di proprietà stessa. <br/> Ad esempio: restituzione solo tali qualificatori propagati dalla definizione della classe. <br/> Per una classe: restituiscono solo i nomi di qualificatore ereditati dalle classi padre. |

`pstrNames` [out] Un nuovo `SAFEARRAY` che contiene i nomi richiesti. La matrice può contenere 0 elementi. Se si verifica un errore, un nuovo `SAFEARRAY` non viene restituito.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per avviare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) metodo.

Dopo aver recuperato i nomi di qualificatore, è possibile accedere in base al nome ogni qualificatore chiamando il [QualifierSet_Get](qualifierset-get.md) (funzione). 

Non è un errore di un determinato oggetto di qualificatori di zero, pertanto il numero di stringhe in `pstrNames` restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
