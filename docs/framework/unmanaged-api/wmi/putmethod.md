---
title: Funzione PutMethod (riferimenti alle API non gestite)
description: La funzione PutMethod crea un metodo.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutMethod
helpviewer_keywords: PutMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 64e43165b34b74540931b308100c9ca942946bcf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
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
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`wszName`  
[in] Il nome del metodo da creare. 

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pSignatureIn`  
[in] Un puntatore a una copia del [classe di sistema Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) che contiene il `in` parametri per il metodo. Questo parametro viene ignorato se impostato su `null`.  

`pSignatureOut`  
[in]  Un puntatore a una copia del [classe di sistema Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) che contiene il `out` parametri per il metodo. Questo parametro viene ignorato se impostato su `null`.
 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Il `[in, out]` parametro del metodo specificato in entrambe le *pInSignature* e *pOutSignature* oggetti hanno qualificatori diversi.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Manca la specifica di un parametro del metodo di **ID** qualificatore. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | La serie di ID assegnato ai parametri del metodo non è consecutiva o non iniziano da 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Il valore restituito per un metodo ha un **ID** qualificatore. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Si è verificato un tentativo di riutilizzare un nome di metodo esistente da una classe padre e le firme non corrispondono. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) metodo.

Questa chiamata al metodo è supportata solo se `ptr` è una definizione di classe CIM. Manipolazione di metodo non è disponibile da [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) puntatori che puntano a istanze CIM.

Gli utenti non è possibile creare metodi con nomi che iniziano o terminano con un carattere di sottolineatura. Questo è riservato per le proprietà e le classi di sistema.

Per un metodo, il `in` e `out` sono descritti i parametri come proprietà in [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) oggetti.

Un `[in/out]` parametro può essere definito aggiungendo la stessa proprietà a entrambi gli oggetti a cui fa riferimento il `pInSignature` e `pOutSignature` parametri. In questo caso, le proprietà condividono lo stesso **ID** valore qualificatore.

Ogni proprietà in un [Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) classe oggetto diverso da `ReturnValue` deve avere un **ID** qualificatore, un valore numerico in base zero che identifica l'ordine in cui vengono visualizzati i parametri. Nessun due parametri possono avere lo stesso **ID** valore e nessun **ID** valore può essere ignorato. Se si verifica una delle due condizioni, il `PutMethod` risultato della funzione `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Esempio

Per un esempio, vedere il [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
