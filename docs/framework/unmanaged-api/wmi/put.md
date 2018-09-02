---
title: Funzione Put (riferimenti alle API non gestite)
description: La funzione Put assegna un nuovo valore per una proprietà denominata.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec8fe889885b555cbf9a95cd34b7330efff27f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43460985"
---
# <a name="put-function"></a>Funzione Put
Imposta una proprietà denominata su un nuovo valore.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszName`  
[in] Il nome della proprietà. Questo parametro non può essere `null`.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pVal`   
[in] Un puntatore a un valore valido `VARIANT` che diventa il nuovo valore della proprietà. Se `pVal` viene `null` o punta a un `VARIANT` typu `VT_NULL`, la proprietà è impostata su `null`. 

`vtType`  
[in] Il tipo della `VARIANT` a cui punta `pVal`. Vedere le [osservazioni](#remarks) sezione per altre informazioni.
 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Il tipo di proprietà non è riconosciuto. Questo valore viene restituito durante la creazione di istanze della classe se la classe esiste già. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Per le istanze: indica che `pVal` punta a un `VARIANT` di un tipo non corretto per la proprietà. <br/> Per le definizioni delle classi: la proprietà esiste già nella classe padre e il nuovo tipo COM è diverso dal vecchio tipo COM. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) (metodo).

Questa funzione sovrascrive sempre il valore della proprietà corrente con uno nuovo. Se il [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a una definizione di classe, `Put` crea o aggiorna il valore della proprietà. Quando [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a un'istanza di CIM `Put` aggiorna il valore della proprietà di sola lettura. `Put` non è possibile creare un valore della proprietà.

Il `__CLASS` proprietà di sistema è solo scrivibile durante la creazione della classe, quando si potrebbe non essere lasciato vuoto. Tutte le altre proprietà di sistema sono di sola lettura.

Un utente non è possibile creare proprietà con nomi che iniziano o terminano con un carattere di sottolineatura ("_"). Questo è riservato per le proprietà e classi di sistema.

Se la proprietà impostata `Put` funzione presente nella classe padre, il valore predefinito della proprietà viene modificato, a meno che il tipo di proprietà non corrisponde al tipo di classe padre. Se la proprietà non esiste e non è un tipo non corrispondente, la proprietà viene creato.

Usare la `vtType` parametro solo durante la creazione di nuove proprietà in una definizione di classe CIM e `pVal` viene `null` o punta a un `VARIANT` di tipo `VT_NULL`. In questo caso, il `vType` parametro specifica il tipo CIM della proprietà. In tutti gli altri casi, `vtType` deve essere 0. `vtType` deve anche essere 0 se l'oggetto sottostante è un'istanza (anche se `Val` è `null`) perché il tipo della proprietà è fisso e non può essere modificato.   

## <a name="example"></a>Esempio

Per un esempio, vedere la [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) (metodo).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
