---
title: Funzione GetNames (riferimenti alle API non gestite)
description: "La funzione GetNames recupera i nomi delle proprietà di un oggetto."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80284900c318a3776168b781ce2e0e5e4a68f96d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getnames-function"></a>GetNames (funzione)
Recupera un subset o tutti i nomi delle proprietà di un oggetto. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`wszQualifierName`  
[in] Un puntatore a un oggetto valido `LPCWSTR` che specifica un nome di qualificatore che agisce come parte di un filtro. Per ulteriori informazioni, vedere il [osservazioni](#remarks) sezione. Questo parametro può essere `null`. 

`lFlags`  
[in] Una combinazione dei campi di bit. Per ulteriori informazioni, vedere il [osservazioni](#remarks) sezione.

`pQualifierValue`   
[in] Un puntatore a un oggetto valido `VARIANT` struttura inizializzato con un valore di filtro. Questo parametro può essere `null`. 

`pstrNames`  
[out] Oggetto `SAFEARRAY` struttura che contiene i nomi delle proprietà. In ingresso, questo parametro deve essere sempre un puntatore a `null`. Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono o è stata specificata una combinazione dei flag e i parametri non corretta. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) metodo.

Viene controllata denominata restituito da una combinazione di flag e i parametri. Ad esempio, la funzione può restituire i nomi di tutte le proprietà o solo i nomi delle proprietà chiave.  Filtro primario è incluso il `lFlags` parametro e gli altri parametri dipendono.

I valori di flag `lFlags` sono campi di bit


I flag che possono essere passati come i `lEnumFlags` argomento sono campi di bit che sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.  È possibile combinare un flag di ogni gruppo con un flag da qualsiasi altro gruppo. Tuttavia, i flag dello stesso gruppo si escludono a vicenda. 

| Flag di gruppo 1 |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Restituisce i nomi delle proprietà. `strQualifierName`e `pQualifierVal` inutilizzati. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Restituire solo le proprietà che hanno un qualificatore del nome specificato per il `strQualifierName` parametro. Se questo flag viene utilizzato, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Restituire solo le proprietà che non dispongono di un qualificatore del nome specificato per il `strQualifierName` parametro. Se questo flag viene utilizzato, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Restituire solo le proprietà che dispongono di un qualificatore del nome specificato per il `wszQualifierName` parametro e avere un valore identico a quello specificato dal `pQualifierVal` struttura. Se questo flag viene utilizzato, è necessario specificare sia un `wszQualifierName` e `pQualifierValue`. |

| Gruppo 2 flag |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Restituire solo i nomi di proprietà che definiscono le chiavi. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Restituito solo nomi di proprietà che sono riferimenti a oggetti. |

| Gruppo 3 flag |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi di proprietà che appartengono alla classe più derivata. Escludere le proprietà delle classi padre. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Restituire solo i nomi di proprietà che appartengono alle classi padre. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Restituire solo i nomi di proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Restituire solo i nomi di proprietà non di sistema. |

La funzione alloca sempre un nuovo `SAFEARRAY` se restituisce `WBEM_S_NO_ERROR`, e `pstrNames` è sempre impostata su di esso. La matrice restituita può essere 0 elementi se non esistono proprietà corrispondenti ai filtri specificati. Se la funzione restituisce un valore diverso da `WBM_S_NO_ERROR`, un nuovo `SAFEARRAY` struttura non viene restituita.
 
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
