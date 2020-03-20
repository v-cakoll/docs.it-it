---
title: Funzione GetObjectText (riferimenti alle API non gestite)
description: La funzione GetObjectText restituisce un rendering testuale di un oggetto nella sintassi MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176786"
---
# <a name="getobjecttext-function"></a>Funzione GetObjectText
Restituisce un rendering testuale dell'oggetto nella sintassi MOF (Managed Object Format).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Normalmente 0. Se `WBEM_FLAG_NO_FLAVORS` viene specificato (o 0x1), i qualificatori vengono inclusi senza informazioni di propagazione o sapore.

`pstrObjectText`[fuori] Puntatore a `null` un'immissione in on. Al ritorno, un `BSTR` nuovo allocato che contiene un rendering della sintassi MOF dell'oggetto.  

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | C'è stato un fallimento generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l’operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .

Il testo MOF restituito non contiene tutte le informazioni sull'oggetto, ma solo informazioni sufficienti per consentire al compilatore MOF di ricreare l'oggetto originale. Ad esempio, non sono inclusi qualificatori propagati o proprietà della classe padre.

Il seguente algoritmo viene utilizzato per ricostruire il testo dei parametri di un metodo:

1. I parametri vengono risequenziati nell'ordine dei relativi valori di identificazione.
1. I parametri specificati `[in]` `[out]` come e vengono combinati in un unico parametro.

`pstrObjectText`deve essere un `null` puntatore a un quando viene chiamata la funzione; non deve puntare a una stringa valida prima della chiamata al metodo, perché il puntatore non verrà deallocato.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
