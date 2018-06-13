---
title: Funzione QualifierSet_Next (riferimenti alle API non gestite)
description: La funzione QualifierSet_Next recupera il qualificatore di un'enumerazione successivo.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8232691c697c51b5a480a68c6d952f294a63460
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460227"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next (funzione)
Recupera il qualificatore di un'enumerazione che ha avviato con una chiamata al successivo il [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (funzione).   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`   
[in] Questo parametro è inutilizzato.

`ptr`   
[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.

`lFlags`   
[in] Riservato. Questo parametro deve essere 0.

`pstrName`   
[out] Il nome del qualificatore. Se `null`, questo parametro viene ignorato; in caso contrario, `pstrName` non deve fare riferimento a un oggetto valido `BSTR` o si verifica una perdita di memoria. Se non è null, la funzione alloca sempre un nuovo `BSTR` quando restituisce `WBEM_S_NO_ERROR`.

`pVal`   
[out] Al termine, il valore per il qualificatore. Se la funzione ha esito negativo, il `VARIANT` a cui puntava `pVal` non viene modificato. Se questo parametro è `null`, il parametro viene ignorato.

`plFlavor`   
[out] Puntatore a un valore LONG che riceve il contrassegno qualificatore. Se non si desiderano informazioni di versione, questo parametro può essere `null`. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Il chiamante non ha chiamato [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per avviare una nuova enumerazione. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non più qualificatori vengono lasciati nell'enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) metodo.

Chiamare il `QualifierSet_Next` funzione ripetutamente per enumerare tutti i qualificatori fino a quando la funzione restituita `WBEM_S_NO_MORE_DATA`. Per terminare in anticipo l'enumerazione, chiamare il [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) (funzione).

L'ordine dei qualificatori restituito durante l'enumerazione è definito.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
