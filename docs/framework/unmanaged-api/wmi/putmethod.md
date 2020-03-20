---
title: PutMethod function (Unmanaged API Reference)
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
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174914"
---
# <a name="putmethod-function"></a>Funzione PutMethod
Crea un metodo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi  
  
```cpp  
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
[in] Questo parametro non viene utilizzato.

`ptr`  
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`  
[in] Nome del metodo da creare.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pSignatureIn`  
[in] Puntatore a una copia della classe `in` di sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) che contiene i parametri per il metodo. Questo parametro viene `null`ignorato se impostato su .  

`pSignatureOut`  
[in]  Puntatore a una copia della classe `out` di sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) che contiene i parametri per il metodo. Questo parametro viene `null`ignorato se impostato su .

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Il `[in, out]` parametro del metodo specificato in entrambi gli oggetti *pInSignature* e *pOutSignature* hanno qualificatori diversi.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | In un parametro del metodo manca la specifica del qualificatore **DI ID.** |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie di ID assegnata ai parametri del metodo non è consecutiva o non inizia da 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Il valore restituito per un metodo ha un qualificatore **di ID.** |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | È stato effettuato un tentativo di riutilizzare un nome di metodo esistente da una classe padre e le firme non corrispondono. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo. |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

Questa chiamata al metodo `ptr` è supportata solo se è una definizione di classe CIM. La modifica del metodo non è disponibile dai puntatori [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che puntano a istanze CIM.

Gli utenti non possono creare metodi con nomi che iniziano o terminano con un segno di sottolineatura. Questa operazione è riservata alle classi e alle proprietà di sistema.

Per un metodo, i `in` parametri e `out` vengono descritti come proprietà negli oggetti [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

Un `[in/out]` parametro può essere definito aggiungendo la stessa `pInSignature` proprietà `pOutSignature` a entrambi gli oggetti a cui puntano i parametri e . In questo caso, le proprietà condividono lo stesso valore del qualificatore **ID.**

Ogni proprietà in un oggetto `ReturnValue` di classe [__Parameters](/windows/desktop/WmiSdk/--parameters) diverso da deve avere un qualificatore **ID,** un valore numerico in base zero che identifica l'ordine in cui vengono visualizzati i parametri. Due parametri non possono avere lo stesso valore **ID** e nessun valore **ID** può essere ignorato. Se si verifica `PutMethod` una `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`delle condizioni, la funzione restituisce .

## <a name="example"></a>Esempio

Per un esempio, vedere il [metodo IWbemClassObject::PutMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
