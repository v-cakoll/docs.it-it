---
title: Funzione GetPropertyQualifierSet (riferimenti alle API non gestite)
description: "La funzione GetPropertyQualifierSet recupera il qualificatore di impostazione per una proprietà."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyQualifierSet
helpviewer_keywords: GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ca2981c8833abaafd5d206b66d6e91f34e2c91d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyqualifierset-function"></a>GetPropertyQualifierSet (funzione)
Recupera il qualificatore impostato per una particolare proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`wszMethod`  
[in] Il nome della proprietà. `wszProperty`deve puntare a un oggetto valido `LPCWSTR`. 

`ppQualSet`  
[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori della proprietà. Il parametro `ppQualSet` non può essere `null`. Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore è impostato in modo che punti a `null`. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non esiste. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | È un parametro `null`. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | La funzione tenta di ottenere i qualificatori di una proprietà di sistema. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) metodo. 

Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM. Modifica di metodo non è disponibile per [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters che puntano a istanze CIM.

Poiché ogni metodo può avere un proprio qualificatori, il [IWbemQualifierSet puntatore](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.

Poiché le proprietà di sistema non dispongono di alcun qualificatori, la funzione restituisce `WBEM_E_SYSTEM_PROPERTY` se si tenta di ottenere un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) puntatore per una proprietà di sistema.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
