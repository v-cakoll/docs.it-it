---
title: Funzione GetPropertyHandle (riferimenti alle API non gestite)
description: "La funzione GetPropertyHandle restituisce un handle univoco che una proprietà di identità."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle (funzione)
Restituisce un handle univoco che identifica una proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) istanza.

`wszPropertyName`  
[in] Una stringa con terminazione null di characaters codificata in formato UTF16 che contiene il nome della proprietà.   

`pType`  
[out] Un puntatore a un [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) membro di enumerazione che rappresenta il tipo CIM della proprietà.

`pHandle`   
[out] Un puntatore a un intero che contiene l'handle di proprietà.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il nome della proprietà specificato non è stato trovato. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | La proprietà richiesta è di tipo sono `CIM_OBJECT` o `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) metodo.

È possibile utilizzare questo handle per identificare le proprietà quando si utilizza [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) metodi per leggere o scrivere i valori delle proprietà.

Handle possono essere recuperati per le proprietà di tutti i tipi di dati diverso da `CIM_OBJECT` e `CIM_ARRAY`. Restituito lavoro handle per tutte le istanze di una classe.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
