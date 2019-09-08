---
title: Funzione VerifyClientKey (riferimenti alle API non gestite)
description: La funzione VerifyClientKey garantisce che la chiave client disponga della sicurezza corretta.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b674e959ab93cf76b84e2af41e875a50b7d115f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798195"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey (funzione)
Verifica che la chiave client includa la sicurezza corretta.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore `ERROR_SUCCESS` restituito è (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *Winerror. h*.

## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.def  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
