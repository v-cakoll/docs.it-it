---
title: Funzione BeginMethodEnumeration (riferimenti alle API non gestite)
description: La funzione BeginMethodEnumeration avvia un'enumerazione dei metodi dell'oggetto
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d6de2a5ff4d2743c7aca2e46b3af848138c15fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158782"
---
# <a name="beginenumeration-function"></a>Funzione BeginEnumeration
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
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`lEnumFlags`  
[in] Zero (0) per tutti i metodi, o un flag che specifica l'ambito dell'enumerazione. I flag seguenti sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limitare l'enumerazione per i metodi definiti nella classe stessa. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limitare l'enumerazione delle proprietà ereditate dalle classi di base. |

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lEnnumFlags` è diverso da zero e non è uno dei flag specificati. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) (metodo).

Questa chiamata al metodo è supportata solo se l'oggetto corrente è una definizione di classe. Manipolazione di metodo non è disponibile dal [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze. L'ordine in cui vengono enumerati i metodi è garantito a essere invariante per una determinata istanza del [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
