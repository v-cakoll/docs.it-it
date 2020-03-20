---
title: Clone function (Unmanaged API Reference)
description: La funzione Clone restituisce un nuovo oggetto che è un clone completo di quello corrente.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176851"
---
# <a name="clone-function"></a>Funzione Clone
Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`ppCopy`  
[fuori] Un nuovo oggetto che è `ptr`un completo solitario di . Questo argomento `null` non può essere se riceve la copia dell'oggetto corrente.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | C'è stato un fallimento generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `null`è stato specificato come parametro e non è legale in questo utilizzo. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Non è disponibile memoria sufficiente per clonare l'oggetto. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)

L'oggetto clonato è un oggetto COM con un conteggio dei riferimenti pari a 1.The cloned object is a COM object that has a reference count of 1.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
