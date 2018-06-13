---
title: Funzione ResetSecurity (riferimenti alle API non gestite)
description: La funzione ResetSecurity assegna un token di rappresentazione per il thread corrente.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31e42b9e39ddb43025e18888572c394d742e38cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457906"
---
# <a name="resetsecurity-function"></a>ResetSecurity (funzione)
Assegna il token di rappresentazione fornito per il thread corrente.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a>Parametri

`token`  
[in] Il token di rappresentazione per associare il thread corrente. Il valore può essere `null`. 

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni dettagliate sull'errore, chiamare il [GetErrorInfo](geterrorinfo.md) (funzione).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
