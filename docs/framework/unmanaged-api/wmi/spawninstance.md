---
title: Funzione SpawnInstance (riferimenti alle API non gestite)
description: La funzione SpawnInstance crea una nuova istanza della classe.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnInstance
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnInstance
helpviewer_keywords: SpawnInstance function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68508f3000e7f4ac481f940ef4c715366c37125c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="spawninstance-function"></a>Funzione SpawnInstance
Crea una nuova istanza di una classe.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`ppNewInstance`  
[out] Riceve il puntatore a una nuova istanza della classe. Se si verifica un errore, non è un nuovo oggetto restituito, e `ppNewInstance` è invariato a sinistra.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr`non è una definizione di classe valido e non può generare nuove istanze. È incompleto o non è stato registrato con WMI chiamando [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` è `null`. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject:: SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) metodo.

`ptr`deve essere una definizione di classe ottenuta dalla gestione di Windows. Si noti che la generazione di un'istanza da un'istanza è supportata ma l'istanza restituita è vuota. È quindi possibile utilizzare la definizione di classe per creare nuove istanze. Una chiamata al [PutInstanceWmi](putinstancewmi.md) è la funzione se si prevede di scrivere l'istanza di gestione di Windows.




Il nuovo oggetto restituito `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente. Impossibile eseguire l'override di questo comportamento. Non vi è alcun altro metodo per cui è possono creare le sottoclassi (classi derivate).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
