---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo Confronta un oggetto in un altro oggetto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bde25ae7455dd7fe35fe1a0a43bb2a6b560c0e3e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064946"
---
# <a name="compareto-function"></a>CompareTo (funzione)
Confronta un oggetto con un altro oggetto di Gestione Windows.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`flags`  
[in] Combinazione bit per bit di flag che specificano le caratteristiche dell'oggetto da prendere in considerazione per il confronto. Vedere le [osservazioni](#remarks) sezione per altre informazioni.

`pCompareTo`  

[in] Oggetto per il confronto. `pcompareTo` deve essere un valore valido [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) dell'istanza; non può essere `null`.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non valido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Gli oggetti sono diversi. |
| `WBEM_S_SAME` | 0 | Gli oggetti corrispondono in base ai flag di confronto. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) (metodo).

I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice. È possibile specificare le caratteristiche singole coinvolti nel confronto specificando una combinazione bit per bit dei flag seguenti:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Ignorare l'origine (server e lo spazio dei nomi da cui provengono). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Ignora tutti i qualificatori (incluso **Key** e **dinamico**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Ignora valori predefiniti delle proprietà. Questo flag si applica solo al confronto delle classi. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Ignora contrassegno qualificatore. Questo flag ancora qualificatori di prende in considerazione, ma ignora le distinzioni tra le quali le regole di propagazione e ignorare le restrizioni. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Ignora maiuscole/minuscole nel confronto dei valori di stringa. Questo vale sia per le stringhe e valori di qualificatore. Il confronto dei nomi di proprietà e il qualificatore è sempre tra maiuscole e minuscole indipendentemente dal fatto che questo flag è impostato. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Si supponga che gli oggetti da confrontare siano istanze della stessa classe. Di conseguenza, questo flag vengono confrontate solo informazioni relativa all'istanza. Usare questo flag per ottimizzare le prestazioni. Se gli oggetti non sono della stessa classe, i risultati sono indefiniti. |

In alternativa, è possibile specificare un singolo flag composito, come indicato di seguito:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Prendere in considerazione tutte le funzionalità nel confronto. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
