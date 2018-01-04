---
title: Funzione BeginMethodEnumeration (riferimenti alle API non gestite)
description: La funzione BeginMethodEnumeration avvia un'enumerazione dei metodi dell'oggetto
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginMethodEnumeration
helpviewer_keywords: BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d843c40a8ab0dd1c48a08126b8c7472505a1732
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a>BeginEnumeration (funzione)
Avvia un'enumerazione dei metodi disponibili per l'oggetto.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lEnumFlags`  
[in] Zero (0) per tutti i metodi o di un flag che specifica l'ambito dell'enumerazione. I flag seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione per i metodi definiti nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione di proprietà ereditate dalle classi di base. |

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lEnnumFlags`è diverso da zero e non è uno dei flag specificati. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) metodo.

Questa chiamata al metodo è supportata solo se l'oggetto corrente è una definizione di classe. Manipolazione di metodo non è disponibile da [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) puntatori che puntano alle istanze. L'ordine in cui vengono enumerati i metodi è sicuramente invariante per una determinata istanza di [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
