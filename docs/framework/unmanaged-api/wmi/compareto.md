---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo Confronta un oggetto a un altro oggetto WMI.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CompareTo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CompareTo
helpviewer_keywords: CompareTo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dacb1516bebfc73ae9e16b03f3755ab49382e571
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="compareto-function"></a>CompareTo (funzione)
Confronta un oggetto a un altro oggetto di gestione di Windows.  

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
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`flags`  
[in] Combinazione bit per bit di flag che specificano le caratteristiche di oggetto da prendere in considerazione per il confronto. Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.

`pCompareTo`  

[in] Oggetto per il confronto. `pcompareTo`deve essere un valore valido [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) dell'istanza; non può essere `null`.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non valido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `BeginEnumeration` è stato eseguito senza una corrispondente chiamata a [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Gli oggetti sono diversi. |
| `WBEM_S_SAME` | 0 | Gli oggetti sono uguali in base ai flag di confronto. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) metodo.

I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice. È possibile specificare le caratteristiche singole coinvolti nel confronto specificando una combinazione bit per bit dei flag seguenti:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Ignorare l'origine (il server e lo spazio dei nomi da cui provengono). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Ignorare tutti i qualificatori (inclusi **chiave** e **dinamica**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Ignora valori predefiniti delle proprietà. Questo flag si applica solo al confronto delle classi. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Ignorare versioni del qualificatore. Questo flag ancora considerando qualificatori, ma ignora le distinzioni tra le quali le regole di propagazione e ignorare le restrizioni. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Ignorare i casi il confronto dei valori di stringa. Questo vale sia per le stringhe e valori del qualificatore. Il confronto dei nomi di proprietà e il qualificatore è sempre tra maiuscole e minuscole indipendentemente dal fatto se questo flag è impostato. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Si supponga che gli oggetti confrontati sono istanze della stessa classe. Di conseguenza, questo flag confronta solo informazioni correlate all'istanza. Utilizzare questo flag per ottimizzare le prestazioni. Se gli oggetti non sono della stessa classe, i risultati sono indefiniti. |

In alternativa, è possibile specificare un solo flag composito come indicato di seguito:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Prendere in considerazione tutte le funzionalità di confronto. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
