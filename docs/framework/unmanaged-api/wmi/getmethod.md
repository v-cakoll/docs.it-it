---
title: Funzione GetMethod (riferimenti alle API non gestite)
description: La funzione GetMethod recupera informazioni su un metodo.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65b8cb74a028892a3494e818f2b523f75e8766a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460447"
---
# <a name="getmethod-function"></a>GetMethod (funzione)
Recupera le informazioni relative al metodo specificato.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`wszName`  
[in] Il nome del metodo. Questo parametro non può essere `null` e deve puntare a un oggetto valido `LPCWSTR`.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`ppInSignature`   
[out] Un puntatore all'indirizzo di un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza che descrive il paramteers al metodo. Questo parametro viene ignorato se è impostato su `null`. 

`ppOutSignature`  
[out] Un puntatore all'indirizzo di un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza che descrive i parametri out al metodo. Questo parametro viene ignorato se è impostato su `null`. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non è stata trovata. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) metodo.

Gestione di Windows è possibile impostare il [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) puntatore a `null` se il metodo ha alcun parametro in.

In `ppInSignature` e `ppOutSignature` descrivono i parametri, in e out rispettivamente come proprietà in un `IWbemClassObject` istanza della classe di sistema [Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx). Le proprietà in `ppInsignature` sono denominati **Param * * * n*, dove *n* è la posizione del parametro nella firma del metodo (ad esempio `Param1`, `Param2`, ecc.). Le proprietà in `ppOutSignature` sono denominate anche **Param * * * n*, e il valore restituito viene denominato **ReturnValue**. Per ulteriori informazioni e un esempio, vedere [IWbemClassObject::GetMethod metodo](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
