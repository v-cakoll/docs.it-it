---
title: Funzione DeleteMethod (riferimenti alle API non gestite)
description: La funzione DeleteMethod Elimina il metodo specificato da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb7b800bca1957c8c324ddb9c11cb4eabb49cd24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628487"
---
# <a name="deletemethod-function"></a>DeleteMethod (funzione)
Elimina il metodo specificato da una definizione di classe CIM.

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
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszName`  
[in] Il nome del metodo da rimuovere dalla tabella della classe. `wszName` deve essere un puntatore a un valore valido `LPCWSTR`.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non esiste. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Non è disponibile memoria sufficiente per completare l'operazione. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) (metodo).

L'eliminazione di metodo non è supportata per [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze CIM.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche
- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
