---
title: Metodo ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151801"
---
# <a name="icordebugcontrollerdetach-method"></a>Metodo ICorDebugController::Detach
Scollega debugger dal dominio dell'applicazione o processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Note  
 Il processo o dominio applicazione continua l'esecuzione in genere, ma l'oggetto "ICorDebugProcess" o "ICorDebugAppDomain" non è più valido e si verificherà alcun callback ulteriormente.  
  
 In .NET Framework versione 2.0, se il debug non gestito è abilitato, questo metodo avrà esito negativo a causa di limitazioni del sistema operativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
