---
title: Funzione GetErrorInfo (riferimenti alle API non gestite)
description: La funzione GetErrorInfo recupera informazioni sull'errore nella chiamata alla funzione precedente.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetErrorInfo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetErrorInfo
helpviewer_keywords: GetErrorInfo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b4acde080c61fbfd5cec319c1986b8c86352c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
