---
title: Funzione QualifierSet_Next (riferimenti alle API non gestite)
description: La funzione QualifierSet_Next recupera il qualificatore successivo in un'enumerazione.
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
ms.openlocfilehash: 35ab5b64b3c7e364e0dd11c002b87a0a413f4335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532435"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next (funzione)
Recupera il qualificatore successivo in un'enumerazione avviata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).   

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
[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.

`lFlags`   
[in] Riservato. Questo parametro deve essere 0.

`pstrName`   
[out] Il nome del qualificatore. Se `null`, questo parametro viene ignorato; in caso contrario, `pstrName` non deve puntare a un valore valido `BSTR` o si verifica una perdita di memoria. Se non è null, la funzione alloca sempre una nuova `BSTR` quando viene restituito `WBEM_S_NO_ERROR`.

`pVal`   
[out] Al termine, il valore del qualificatore. Se la funzione ha esito negativo, il `VARIANT` a cui punta `pVal` non viene modificato. Se questo parametro è `null`, il parametro viene ignorato.

`plFlavor`   
[out] Puntatore a un valore LONG che riceve il contrassegno qualificatore. Se non si desiderano informazioni di versione, questo parametro può essere `null`. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Il chiamante non ha chiamato [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per iniziare una nuova enumerazione. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Nessun altri qualificatori vengono lasciati nell'enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) (metodo).

Si chiama il `QualifierSet_Next` funzione più volte per enumerare tutti i qualificatori finché la funzione restituita `WBEM_S_NO_MORE_DATA`. Per terminare l'enumerazione all'inizio, chiamare il [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) (funzione).

L'ordine dei qualificatori restituito durante l'enumerazione è definito.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche
- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
