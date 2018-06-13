---
title: Funzione GetErrorInfo (riferimenti alle API non gestite)
description: La funzione GetErrorInfo recupera informazioni sull'errore nella chiamata alla funzione precedente.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef52a4e503597e08eae407571f02bf63adafc4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455957"
---
# <a name="geterrorinfo-function"></a>GetErrorInfo (funzione)
Recupera informazioni sull'errore nella chiamata alla funzione precedente.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a>Valore restituito

Un puntatore a un [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) oggetto se la chiamata di funzione ha esito positivo, o `null` in caso di errore.
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.def  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
