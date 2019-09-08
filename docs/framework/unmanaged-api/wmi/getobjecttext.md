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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d47fcd59204a4d114fc9f0dc5bc4550ba1681f33
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798497"
---
# <a name="getobjecttext-function"></a>Funzione GetObjectText
Restituisce un rendering testuale dell'oggetto nella sintassi Managed Object Format (MOF).

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
in Questo parametro è inutilizzato.

`ptr`  
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
in Normalmente 0. Se `WBEM_FLAG_NO_FLAVORS` viene specificato (o 0x1), i qualificatori vengono inclusi senza informazioni sulla propagazione o sul sapore.

`pstrObjectText`   
out Puntatore a un oggetto `null` nella voce. Al ritorno, un oggetto appena `BSTR` allocato contenente un rendering della sintassi MOF dell'oggetto.  

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametro non valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .

Il testo MOF restituito non contiene tutte le informazioni sull'oggetto, ma solo le informazioni sufficienti per consentire al compilatore MOF di ricreare l'oggetto originale. Ad esempio, non sono inclusi qualificatori propagati o proprietà della classe padre.

Per ricostruire il testo dei parametri di un metodo viene utilizzato l'algoritmo seguente:

1. I parametri vengono risequenziati nell'ordine dei valori dell'identificatore.
1. I parametri specificati come `[in]` e `[out]` vengono combinati in un singolo parametro.
 
`pstrObjectText`deve essere un puntatore a un `null` oggetto quando viene chiamata la funzione. non deve puntare a una stringa valida prima della chiamata al metodo, perché il puntatore non verrà deallocato.

## <a name="requirements"></a>Requisiti  
**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
