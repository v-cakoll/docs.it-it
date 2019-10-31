---
title: Funzione SpawnInstance (riferimenti alle API non gestite)
description: La funzione SpawnInstance crea una nuova istanza di una classe.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f93b4fbd5429ed2bdae8fb707e61df024cd8fd6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107520"
---
# <a name="spawninstance-function"></a>SpawnInstance (funzione)
Crea una nuova istanza di una classe.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
in Questo parametro è inutilizzato.

`ptr`  
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`ppNewInstance`  
out Riceve il puntatore alla nuova istanza della classe. Se si verifica un errore, non viene restituito un nuovo oggetto e `ppNewInstance` viene lasciato invariato.

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` non è una definizione di classe valida e non può generare nuove istanze. È incompleto o non è stato registrato con gestione Windows chiamando [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` è `null`. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) .

`ptr` deve essere una definizione di classe ottenuta dalla gestione di Windows. Si noti che la generazione di un'istanza da un'istanza è supportata, ma l'istanza restituita è vuota. Usare quindi questa definizione di classe per creare nuove istanze. Una chiamata alla funzione [PutInstanceWmi](putinstancewmi.md) è obbligatoria se si intende scrivere l'istanza di in gestione Windows.

Il nuovo oggetto restituito in `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente. Non è possibile eseguire l'override di questo comportamento. Non esiste un altro metodo con cui è possibile creare sottoclassi (classi derivate).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
