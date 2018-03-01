---
title: Initialize (funzione) (riferimenti alle API non gestite)
description: La funzione di inizializzazione esegue l'inizializzazione di WMI.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d62d959c5dfeac237abb20b86df87ae07a077dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="initialize-function"></a>Initialize (funzione)
Esegue l'inizializzazione di WMI.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a>Parametri

`bAllowIManagementObjectQI`   
[in] `true` per indicare che sono consentite chiamate a QueryInterface su oggetti WMI; `false` in caso contrario.

## <a name="return-value"></a>Valore restituito

La funzione restituisce sempre `S_OK` (0).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.def  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
