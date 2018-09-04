---
title: Funzione GetMethodOrigin (riferimenti alle API non gestite)
description: La funzione GetMethodOrigin determina la classe in cui viene dichiarato un metodo.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1cc754fcf7d1defa815bb0a74b7c2b4a6909478
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539328"
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin (funzione)
Determina la classe in cui viene dichiarato un metodo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszMethodName`  
[in] Il nome del metodo per l'oggetto la cui classe proprietaria è richiesto. 

`pstrClassName`  
[out] Riceve il nome della classe cui appartiene il metodo.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non è stato trovato. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) (metodo).

Poiché una classe può ereditare i metodi da una o più classi base, gli sviluppatori spesso vogliono determinare la classe in cui è definito un metodo specifico.

Il `pstrClassName` parametro non deve puntare a un valore valido `BSTR` prima di chiamare la funzione poiché si tratta di un `out` parametro; questo puntatore non viene deallocato dopo la funzione restituisce.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
