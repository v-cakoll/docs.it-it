---
title: GetNames function (Unmanaged API Reference)
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174953"
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
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszQualifierName`  
[in] Puntatore a `LPCWSTR` un oggetto valido che specifica un nome di qualificatore che opera come parte di un filtro. Per ulteriori informazioni, vedere la sezione [Osservazioni.](#remarks) Questo parametro può essere `null`.

`lFlags`  
[in] Combinazione di campi di bit. Per ulteriori informazioni, vedere la sezione [Osservazioni.](#remarks)

`pQualifierValue`[in] Puntatore a `VARIANT` una struttura valida inizializzata su un valore di filtro. Questo parametro può essere `null`.

`pstrNames`  
[fuori] Struttura `SAFEARRAY` che contiene i nomi delle proprietà. All'ingresso, questo parametro deve `null`essere sempre un puntatore a . Vedere la sezione [Osservazioni](#remarks) per ulteriori informazioni.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | C'è stato un fallimento generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi oppure è stata specificata una combinazione non corretta di flag e parametri. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l’operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .

Il nome restituito è controllato da una combinazione di flag e parametri. Ad esempio, la funzione può restituire i nomi di tutte le proprietà o solo i nomi delle proprietà chiave.  Il filtro primario `lFlags` viene specificato nel parametro e gli altri parametri variano a seconda di esso.

I valori `lFlags` dei flag in sono campi di bit

I flag che possono `lEnumFlags` essere passati come argomento sono campi di bit definiti nel file di intestazione *WbemCli.h* oppure è possibile definirli come costanti nel codice.  È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo. Tuttavia, i flag dello stesso gruppo si escludono a vicenda.

| Contrassegni gruppo 1 |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Restituire tutti i nomi di proprietà. `strQualifierName`e `pQualifierVal` sono inutilizzati. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Restituire solo le proprietà con un qualificatore del nome specificato dal `strQualifierName` parametro. Se si utilizza questo flag, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Restituisce solo le proprietà che non dispongono `strQualifierName` di un qualificatore del nome specificato dal parametro. Se si utilizza questo flag, è necessario specificare `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Restituire solo le proprietà che hanno un `wszQualifierName` qualificatore del nome specificato dal `pQualifierVal` parametro e hanno anche un valore identico a quello specificato dalla struttura. Se viene utilizzato questo flag, `wszQualifierName` è `pQualifierValue`necessario specificare sia a che un oggetto . |

| Contrassegni del gruppo 2 |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Restituire solo i nomi delle proprietà che definiscono le chiavi. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Restituire solo i nomi di proprietà che sono riferimenti a oggetti. |

| Contrassegni gruppo 3 |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi di proprietà che appartengono alla classe più derivata. Escludere le proprietà dalle classi padre. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Restituire solo i nomi di proprietà che appartengono alle classi padre. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 (in modo 0x30) | Restituire solo i nomi delle proprietà di sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Restituire solo i nomi delle proprietà non di sistema. |

La funzione alloca `SAFEARRAY` sempre un `WBEM_S_NO_ERROR`nuovo `pstrNames` se restituisce ed è sempre impostata in modo che punti a essa. La matrice restituita può avere 0 elementi se nessuna proprietà corrisponde ai filtri specificati. Se la funzione restituisce `WBM_S_NO_ERROR`un `SAFEARRAY` valore diverso da , non viene restituita una nuova struttura.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
