---
title: Funzione QualifierSet_Delete (riferimenti alle API non gestite)
description: La funzione QualifierSet_Delete Elimina un qualificatore in base al nome.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e96ba458edfe7261fd5857b7bcb8486f4a6636
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460045"
---
# <a name="qualifiersetdelete-function"></a>QualifierSet_Delete (funzione)
Elimina un qualificatore specificato in base al nome.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`   
[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.

`wszName`   
[in] Il nome del qualificatore da eliminare.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Il `wszName` parametro non è valido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | L'eliminazione di questo qualificatore non è valido. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il qualificatore specificato non è stato trovato. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | La sostituzione locale è stata eliminata e il qualificatore originale dall'oggetto padre ha ripreso l'ambito. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) metodo.

A causa delle regole di propagazione qualificatore, un qualificatore specifico può avere stato ereditato da un altro oggetto e semplicemente sottoposto a override nella classe corrente o istanza. In questo caso, il `QualifierSet_Delete` metodo reimposta il qualificatore del valore ereditato originale. In questo caso, la funzione restituisce il codice di stato `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
