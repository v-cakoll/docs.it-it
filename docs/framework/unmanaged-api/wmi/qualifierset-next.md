---
title: Funzione QualifierSet_Next (riferimenti alle API non gestite)
description: La funzione QualifierSet_Next Recupera il qualificatore successivo in un'enumerazione.
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
ms.openlocfilehash: f97a19f236b87a7f4c5b2014aca6ee4abd338c63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798278"
---
# <a name="qualifierset_next-function"></a>QualifierSet_Next (funzione)
Recupera il qualificatore successivo in un'enumerazione avviata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
in Questo parametro è inutilizzato.

`ptr`   
in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`   
[in] Riservato. Questo parametro deve essere 0.

`pstrName`   
out Nome del qualificatore. Se `null`, questo parametro viene ignorato; in caso `pstrName` contrario, non deve puntare a `BSTR` una perdita di memoria o valida. Se non è null, la funzione alloca sempre un nuovo `BSTR` oggetto quando restituisce `WBEM_S_NO_ERROR`.

`pVal`   
out In caso di esito positivo, il valore per il qualificatore. Se la funzione `pVal` ha esito `VARIANT` negativo, l'oggetto a cui fa riferimento non viene modificato. Se questo parametro è `null`, il parametro viene ignorato.

`plFlavor`   
out Puntatore a un oggetto LONG che riceve la versione del qualificatore. Se non si desidera ottenere informazioni sul sapore, questo parametro `null`può essere. 

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Il chiamante non ha chiamato [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | La memoria disponibile non è sufficiente per iniziare una nuova enumerazione. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Nessun qualificatore rimanente nell'enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .

Chiamare ripetutamente `QualifierSet_Next` la funzione per enumerare tutti i qualificatori fino a quando `WBEM_S_NO_MORE_DATA`la funzione non restituisce. Per terminare l'enumerazione in anticipo, chiamare la funzione [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .

L'ordine dei qualificatori restituiti durante l'enumerazione non è definito.

## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
