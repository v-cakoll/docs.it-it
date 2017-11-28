---
title: Funzione SetSecurity (riferimenti alle API non gestite)
description: La funzione SetSecurity recupera il token di rappresentazione del thread corrente.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SetSecurity
helpviewer_keywords: SetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4fd7ccb0cfb25773da7e489f9ce4d6332b80a616
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="setsecurity-function"></a>Funzione SetSecurity
Recupera il token di rappresentazione associato al thread corrente.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a>Parametri

`pNeedToReset`[out] Quando la funzione viene restituito, contiene un puntatore a un `boolean` che indica se il token deve essere reimpostato tramite la chiamata di [ResetSecurity](resetsecurity.md) (funzione).  

`token`  
[out] Quando la funzione viene restituito, contiene un puntatore all'handle del token di rappresentazione associato al thread corrente. Il valore può essere `null` se non è disponibile alcun token associato al thread corrente. 

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni dettagliate sull'errore, chiamare il [GetErrorInfo](geterrorinfo.md) (funzione).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
