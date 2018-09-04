---
title: 'IMetaDataImport:: GetNames (funzione) (riferimenti alle API non gestite)'
description: La funzione di GetNames recupera i nomi delle proprietà di un oggetto.
ms.date: 11/06/2017
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
ms.openlocfilehash: f53174bf060938d5a55cbd196944ac11916d59cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661394"
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
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszQualifierName`  
[in] Un puntatore a un valore valido `LPCWSTR` che specifica un nome di qualificatore che opera come parte di un filtro. Per altre informazioni, vedere la [osservazioni](#remarks) sezione. Questo parametro può essere `null`. 

`lFlags`  
[in] Una combinazione dei campi di bit. Per altre informazioni, vedere la [osservazioni](#remarks) sezione.

`pQualifierValue`   
[in] Un puntatore a un valore valido `VARIANT` struttura inizializzata su un valore di filtro. Questo parametro può essere `null`. 

`pstrNames`  
[out] Oggetto `SAFEARRAY` struttura che contiene i nomi delle proprietà. In ingresso, questo parametro deve essere sempre un puntatore a `null`. Vedere le [osservazioni](#remarks) sezione per altre informazioni. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono o è stata specificata una combinazione di flag e i parametri non corretta. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) (metodo).

L'oggetto denominato restituito è controllato da una combinazione di flag e i parametri. Ad esempio, la funzione può restituire i nomi di tutte le proprietà o solo i nomi delle proprietà della chiave.  Filtro primario viene specificato nella `lFlags` parametro e gli altri parametri dipendono.

I valori di flag `lFlags` sono campi di bit


I flag che possono essere passati come le `lEnumFlags` argomenti sono i campi di bit definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.  È possibile combinare un flag di ogni gruppo con eventuali flag da qualsiasi altro gruppo. Tuttavia, i flag dallo stesso gruppo si escludono a vicenda. 

| Flag di gruppo 1 |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Restituire tutti i nomi di proprietà. `strQualifierName` e `pQualifierVal` inutilizzate. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Restituire solo le proprietà che hanno un qualificatore del nome specificato per il `strQualifierName` parametro. Se questo flag viene utilizzato, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Restituire solo le proprietà che non dispongono di un qualificatore del nome specificato per il `strQualifierName` parametro. Se questo flag viene utilizzato, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Restituire solo le proprietà che hanno un qualificatore del nome specificato per il `wszQualifierName` parametro e anche avere un valore identico a quello specificato dal `pQualifierVal` struttura. Se questo flag viene utilizzato, è necessario specificare sia un `wszQualifierName` e un `pQualifierValue`. |

| Flag di gruppo 2 |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Restituire solo i nomi di proprietà che definiscono le chiavi. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Restituito solo nomi di proprietà che sono riferimenti a oggetti. |

| Gruppo 3 flag |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi di proprietà che appartengono alla classe più derivata. Escludere le proprietà delle classi padre. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Restituire solo i nomi di proprietà che appartengono alle classi padre. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Restituire solo i nomi delle proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Restituire solo i nomi di proprietà non di sistema. |

La funzione alloca sempre una nuova `SAFEARRAY` se viene restituito `WBEM_S_NO_ERROR`, e `pstrNames` è sempre impostato in modo che punti a esso. La matrice restituita può contenere elementi 0 se non esistono proprietà corrispondenti ai filtri specificati. Se la funzione restituisce un valore diverso da `WBM_S_NO_ERROR`, un nuovo `SAFEARRAY` struttura non viene restituita.
 
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
