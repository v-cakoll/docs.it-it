---
title: Funzione Delete (riferimenti alle API non gestite)
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
ms.openlocfilehash: a1bf9bd5d93d1affee649588138456269411d280
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798678"
---
# <a name="delete-function"></a>Funzione Delete

Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
in Nome della proprietà da eliminare. `wszName`deve essere un puntatore a un oggetto `LPCWSTR`valido.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Impossibile eliminare la proprietà. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` non è valido. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non esiste. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | La proprietà viene ereditata da una classe base. |
| `WBEM_E_SYSTEM_PROPERTY` | | La proprietà è una proprietà di sistema. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | La funzione ha eliminato un valore predefinito di override per la classe corrente. Il valore predefinito per questa proprietà nella classe padre è stato riattivato. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::D Elimina](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) .

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
