---
title: InheritsFrom function (Unmanaged API Reference)
description: La funzione InheritsFrom determina se una classe o un'istanza deriva da una particolare classe padre.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174940"
---
# <a name="inheritsfrom-function"></a>Funzione InheritsFrom
Determina se la classe o l'istanza corrente deriva da una classe padre specificata.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszAncestor`  
[in] Nome della classe. `wszAncestor`deve puntare a `LPCWSTR`un valore valido .

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | L'oggetto corrente `wszAncestor`eredita da .  |
| `WBEM_S_FALSE` | 1 | L'oggetto corrente non `wszAncestor`eredita da . |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor` è `null`. |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
