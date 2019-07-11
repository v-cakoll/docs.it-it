---
title: Metodo ICorDebugAppDomain::GetId
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb8917fa401db9424cff168fe0b06ad84065827c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737933"
---
# <a name="icordebugappdomaingetid-method"></a>Metodo ICorDebugAppDomain::GetId
Ottiene l'identificatore univoco del dominio dell'applicazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pId`  
 [out] Identificatore univoco del dominio dell'applicazione.  
  
## <a name="remarks"></a>Note  
 L'identificatore per il dominio applicazione è univoco all'interno del processo che lo contiene.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
