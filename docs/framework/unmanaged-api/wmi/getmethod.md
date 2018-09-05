---
title: 'IMetaDataImport:: GetMethod (funzione) (riferimenti alle API non gestite)'
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
ms.openlocfilehash: a913de0ff20fba51295fd8282b58e3953be9bba2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773959"
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
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszName`  
[in] Il nome del metodo. Questo parametro non può essere `null` e deve puntare a un valore valido `LPCWSTR`.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`ppInSignature`   
[out] Un puntatore all'indirizzo di un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza che descrive il paramteers al metodo. Questo parametro viene ignorato se è impostato su `null`. 

`ppOutSignature`  
[out] Un puntatore all'indirizzo di un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza che descrive i parametri out al metodo. Questo parametro viene ignorato se è impostato su `null`. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non è stata trovata. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) (metodo).

Gestione di Windows è possibile impostare il [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatore a `null` se il metodo ha alcun parametro in.

Nelle `ppInSignature` e `ppOutSignature` descrivono in e out parametri, rispettivamente, come proprietà in un `IWbemClassObject` istanza della classe di sistema [parametry](/windows/desktop/WmiSdk/--parameters). Le proprietà nella `ppInsignature` sono denominati **Param * * * n*, dove *n* corrisponde alla posizione del parametro nella firma del metodo (ad esempio `Param1`, `Param2`e così via.). Le proprietà nella `ppOutSignature` sono denominate anche **Param * * * n*, e il valore restituito è denominato **ReturnValue**. Per altre informazioni e un esempio, vedere [IWbemClassObject::GetMethod metodo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
