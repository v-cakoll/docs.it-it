---
title: Eliminare la funzione (riferimenti alle API non gestite)
description: La funzione Delete Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7fcf5cff9f95b06a834d73df4090bd1edfca61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460243"
---
# <a name="delete-function"></a>Eliminare la funzione
Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`wszName`  
[in] Il nome della proprietà da eliminare. `wszName` deve essere un puntatore a un valore valido `LPCWSTR`.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | La proprietà non può essere eliminata. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszzName` non è valido. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non esiste. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Non è disponibile memoria sufficiente per completare l'operazione. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | La proprietà viene ereditata da una classe base. |
| `WBEM_E_SYSTEM_PROPERTY` | | La proprietà è una proprietà di sistema. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | La funzione eliminata di un valore predefinito di sostituzione per la classe corrente. Il valore predefinito per questa proprietà nella classe padre è stata reactiviated. | 

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
