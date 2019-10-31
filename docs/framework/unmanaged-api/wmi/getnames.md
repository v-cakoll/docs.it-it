---
title: Funzione GetNames (riferimenti alle API non gestite)
description: La funzione GetNames recupera i nomi delle proprietà di un oggetto.
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
ms.openlocfilehash: 5b03ed6a68fbe288e93dedb4f425f1511563dfeb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102518"
---
# <a name="getnames-function"></a>Funzione GetNames
Recupera un subset o tutti i nomi delle proprietà di un oggetto. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
in Questo parametro è inutilizzato.

`ptr`  
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszQualifierName`  
in Puntatore a un `LPCWSTR` valido che specifica un nome di qualificatore che opera come parte di un filtro. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) . Questo parametro può essere `null`. 

`lFlags`  
in Combinazione di campi di bit. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

`pQualifierValue`   
in Puntatore a una struttura `VARIANT` valida inizializzata su un valore di filtro. Questo parametro può essere `null`. 

`pstrNames`  
out Struttura `SAFEARRAY` contenente i nomi di proprietà. In ingresso, questo parametro deve essere sempre un puntatore a `null`. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) . 

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi oppure è stata specificata una combinazione non corretta di flag e parametri. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .

Il denominato restituito è controllato da una combinazione di flag e parametri. Ad esempio, la funzione può restituire i nomi di tutte le proprietà o solo i nomi delle proprietà chiave.  Il filtro primario viene specificato nel parametro `lFlags` e gli altri parametri variano a seconda del parametro.

I valori dei flag in `lFlags` sono campi di bit

I flag che possono essere passati come `lEnumFlags` argomento sono i campi di bit definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.  È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo. Tuttavia, i flag dello stesso gruppo si escludono a vicenda. 

| Flag gruppo 1 |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Restituisce tutti i nomi di proprietà. `strQualifierName` e `pQualifierVal` sono inutilizzati. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Restituisce solo le proprietà con un qualificatore del nome specificato dal parametro `strQualifierName`. Se viene utilizzato questo flag, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Restituisce solo le proprietà che non dispongono di un qualificatore del nome specificato dal parametro `strQualifierName`. Se viene utilizzato questo flag, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3\. | Restituire solo le proprietà con un qualificatore del nome specificato dal parametro `wszQualifierName` e avere anche un valore identico a quello specificato dalla struttura `pQualifierVal`. Se viene usato questo flag, è necessario specificare sia un `wszQualifierName` che un `pQualifierValue`. |

| Flag gruppo 2 |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Restituisce solo i nomi delle proprietà che definiscono le chiavi. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Restituisce solo i nomi di proprietà che sono riferimenti a oggetti. |

| Flag gruppo 3 |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituisce solo i nomi di proprietà che appartengono alla classe più derivata. Escludere le proprietà dalle classi padre. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Restituisce solo i nomi delle proprietà che appartengono alle classi padre. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Restituisce solo i nomi delle proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Restituisce solo i nomi delle proprietà non di sistema. |

La funzione alloca sempre un nuovo `SAFEARRAY` se restituisce `WBEM_S_NO_ERROR`e `pstrNames` è sempre impostato in modo che punti a essa. La matrice restituita può avere 0 elementi se nessuna proprietà corrisponde ai filtri specificati. Se la funzione restituisce un valore diverso da `WBM_S_NO_ERROR`, non viene restituita una nuova struttura di `SAFEARRAY`.
 
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
