---
title: Funzione SpawnDerivedClass (riferimenti alle API non gestite)
description: La funzione SpawnDerivedClass crea un nuovo oggetto che deriva da un oggetto.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnDerivedClass
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnDerivedClass
helpviewer_keywords: SpawnDerivedClass function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16f9a762c87e1e181202739b70cd978a80864f04
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass (funzione)
Crea un oggetto appena derivata da un oggetto specificato.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`ppNewClass`  
[out] Riceve il puntatore al nuovo oggetto di definizione di classe. Se si verifica un errore, non è un nuovo oggetto restituito, e `ppNewClass` è invariato a sinistra. Il valore non può essere `null`.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Un'operazione non valida, ad esempio l'installazione di una classe da un'istanza, è stato richiesto. |
| `WBEM_E_INCOMPLETE_CLASS` | La classe di origine non è completamente definita o registrata con gestione di Windows, pertanto non è consentita una nuova classe derivata. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` è `null`. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) metodo.

`ptr`deve essere una definizione di classe che diventa la classe padre dell'oggetto generato. L'oggetto restituito diventa una sottoclasse dell'oggetto corrente.

Il nuovo oggetto restituito `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente. Impossibile eseguire l'override di questo comportamento. Non vi è alcun altro metodo per cui è possono creare le sottoclassi (classi derivate).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
