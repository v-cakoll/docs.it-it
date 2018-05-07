---
title: Funzione GetObjectText (riferimenti alle API non gestite)
description: La funzione GetObjectText restituisce a seguito del rendering testuale di un oggetto in sintassi MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2f0e766a3a310bdb58f7cbffd8d49404eb5e0b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="getobjecttext-function"></a>Funzione GetObjectText
Restituisce un rendering testuale dell'oggetto nella sintassi del formato MOF (Managed Object).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lFlags`  
[in] In genere 0. Se `WBEM_FLAG_NO_FLAVORS` (o 0x1) viene specificato, qualificatori sono inclusi senza informazioni di propagazione o la versione.

`pstrObjectText`   
[out] Un puntatore a un `null` in ingresso. Restituzione, appena allocato `BSTR` che contiene un rendering di sintassi MOF dell'oggetto.  

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) metodo.

Il testo MOF restituito non contiene tutte le informazioni sull'oggetto, ma solo le informazioni sufficienti per il file MOF essere in grado di ricreare l'oggetto originale. Ad esempio, non sono incluse propagati qualificatori o una proprietà della classe padre.

Per ricostruire il testo dei parametri di un metodo, viene utilizzato l'algoritmo seguente:

1. I parametri sono resequenced nell'ordine dei valori dell'identificatore.
1. I parametri vengono specificati come `[in]` e `[out]` vengono combinati in un singolo parametro.
 
`pstrObjectText` deve essere un puntatore a un `null` quando viene chiamata la funzione; non deve puntare a una stringa valida prima della chiamata al metodo, poiché il puntatore non essere deallocato.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
