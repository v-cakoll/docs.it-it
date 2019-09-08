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
ms.openlocfilehash: 4bc26a16650a5beecc17898e0421e79536713deb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798331"
---
# <a name="qualifierset_delete-function"></a>QualifierSet_Delete (funzione)
Elimina un qualificatore specificato in base al nome.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
in Questo parametro è inutilizzato.

`ptr`   
in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName`   
in Nome del qualificatore da eliminare.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |DESCRIZIONE  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Il parametro `wszName` non è valido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | L'eliminazione di questo qualificatore non è valida. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il qualificatore specificato non è stato trovato. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | L'override locale è stato eliminato e il qualificatore originale dall'oggetto padre ha ripreso l'ambito. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet::D Elimina](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .

A causa delle regole di propagazione dei qualificatori, è possibile che un qualificatore specifico sia stato ereditato da un altro oggetto e sottoposto a override nella classe o nell'istanza corrente. In questo caso, il `QualifierSet_Delete` metodo reimposta il qualificatore sul valore ereditato originale. La funzione in questo caso restituisce il codice `WBEM_S_RESET_TO_DEFAULT`di stato.

## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
