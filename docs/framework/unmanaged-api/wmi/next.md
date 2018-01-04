---
title: Funzione Next (riferimenti alle API non gestite)
description: "Retireves di funzione successiva la proprietà successiva in un'enumerazione."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Next
helpviewer_keywords: Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a>Funzione successiva
Recupera la proprietà successiva in un'enumerazione che inizia con una chiamata a [BeginEnumeration](beginenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.

`lFlags`  
[in] Riservato. Questo parametro deve essere 0.

`pstrName`  
[out] Un nuovo `BSTR` che contiene il nome della proprietà. È possibile impostare questo parametro su `null` se il nome non è obbligatorio.

`pVal`  
[out] Oggetto `VARIANT` riempita con il valore della proprietà. È possibile impostare questo parametro su `null` se il valore non è obbligatorio. Se la funzione restituisce un codice di errore, il `VARIANT` passato a `pVal` è invariato a sinistra. 

`pvtType`  
[out] Un puntatore a un `CIMTYPE` variabile (un `LONG` in cui viene inserito il tipo della proprietà). Il valore di questa proprietà può essere un `VT_NULL_VARIANT`, nel qual caso è necessario determinare il tipo effettivo della proprietà. Questo parametro può anche essere `null`. 

`plFlavor`  
[out] `null`, o un valore che riceve le informazioni sull'origine della proprietà. Vedere la sezione [note] per i valori possibili. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non valido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Si è verificato alcuna chiamata al [ `BeginEnumeration` ](beginenumeration.md) (funzione). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per avviare una nuova enumerazione. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | La procedura remota chiamare tra il processo corrente e la gestione di Windows non è riuscita. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non esistono altre proprietà nell'enumerazione. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) metodo.

Questo metodo restituisce anche le proprietà di sistema.

Se il tipo sottostante della proprietà è un percorso dell'oggetto, una data o ora o un altro tipo speciale, il tipo restituito non contiene informazioni sufficienti. Il chiamante deve esaminare il `CIMTYPE` per la proprietà specificata determinare se la proprietà è un riferimento all'oggetto, una data o ora o un altro tipo speciale.

Se `plFlavor` non `null`, `LONG` valore riceve le informazioni relative all'origine della proprietà, come indicato di seguito:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La proprietà è una proprietà di sistema standard. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Per una classe: la proprietà viene ereditata dalla classe padre. </br> Per un'istanza: la proprietà, mentre ereditata dalla classe padre, non è stata modificata dall'istanza.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Per una classe: la proprietà appartiene alla classe derivata. </br> Per un'istanza: la proprietà viene modificata tramite l'istanza. ovvero, è stato fornito un valore o un qualificatore è stato aggiunto o modificato. |

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
