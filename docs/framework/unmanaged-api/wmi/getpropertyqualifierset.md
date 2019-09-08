---
title: Funzione GetPropertyQualifierSet (riferimenti alle API non gestite)
description: La funzione GetPropertyQualifierSet Recupera il set di qualificatori per una proprietà.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798479"
---
# <a name="getpropertyqualifierset-function"></a>GetPropertyQualifierSet (funzione)

Recupera il qualificatore impostato per una particolare proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszMethod`\
in Nome della proprietà. `wszProperty`deve puntare a un oggetto `LPCWSTR`valido.

`ppQualSet`\
out Riceve il puntatore a interfaccia che consente di accedere ai qualificatori della proprietà. Il parametro `ppQualSet` non può essere `null`. Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore è impostato in modo da `null`puntare a.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non esiste. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro è `null`. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | La funzione tenta di ottenere i qualificatori di una proprietà di sistema. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) .

Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM. La manipolazione del metodo non è disponibile per i puntatori [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che puntano a istanze CIM.

Poiché ogni metodo può avere qualificatori propri, il [puntatore IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.

Poiché le proprietà di sistema non hanno qualificatori, la `WBEM_E_SYSTEM_PROPERTY` funzione restituisce se si tenta di ottenere un puntatore [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) per una proprietà di sistema.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
