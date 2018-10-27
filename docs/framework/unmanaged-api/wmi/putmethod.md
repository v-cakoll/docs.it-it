---
title: Funzione PutMethod (riferimenti alle API non gestite)
description: La funzione PutMethod crea un metodo.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98ef688c1136a81a5b57c3fdfee73c53024186e7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50191041"
---
# <a name="putmethod-function"></a>PutMethod (funzione)
Crea un metodo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszName`  
[in] Il nome del metodo da creare. 

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pSignatureIn`  
[in] Un puntatore a una copia del [classe di sistema Parameters](/windows/desktop/WmiSdk/--parameters) che contiene il `in` parametri del metodo. Questo parametro viene ignorato se impostato su `null`.  

`pSignatureOut`  
[in]  Un puntatore a una copia del [classe di sistema Parameters](/windows/desktop/WmiSdk/--parameters) che contiene il `out` parametri del metodo. Questo parametro viene ignorato se impostato su `null`.
 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Il `[in, out]` parametro del metodo specificato in entrambe le *pInSignature* e *pOutSignature* gli oggetti hanno qualificatori diversi.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Un parametro del metodo manca la specifica del **ID** qualificatore. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie di ID viene assegnata ai parametri del metodo non consecutiva o non iniziano da 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Il valore restituito per un metodo ha un **ID** qualificatore. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Si è verificato un tentativo di riusare un nome di metodo esistente da una classe padre e le firme non corrispondono. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) (metodo).

Questa chiamata al metodo è supportata solo se `ptr` è una definizione di classe CIM. Manipolazione di metodo non è disponibile dal [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze CIM.

Gli utenti non è possibile creare metodi con nomi che iniziano o terminano con un carattere di sottolineatura. Questo è riservato per le proprietà e classi di sistema.

Per un metodo, il `in` e `out` sono descritti i parametri come proprietà nella [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) oggetti.

Un' `[in/out]` parametro può essere definito aggiungendo la stessa proprietà per entrambi gli oggetti a cui punta il `pInSignature` e `pOutSignature` parametri. In questo caso, le proprietà condividono lo stesso **ID** valore del qualificatore.

Ogni proprietà in un [Parameters](/windows/desktop/WmiSdk/--parameters) classe oggetto diverso da `ReturnValue` deve avere un' **ID** qualificatore, un valore numerico in base zero che identifica l'ordine in cui vengono visualizzati i parametri. Nessuna due parametri possono avere lo stesso **ID** valore e nessun **ID** valore può essere ignorato. Se si verifica una delle due condizioni, il `PutMethod` funzione restituisce `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Esempio

Per un esempio, vedere la [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) (metodo).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
