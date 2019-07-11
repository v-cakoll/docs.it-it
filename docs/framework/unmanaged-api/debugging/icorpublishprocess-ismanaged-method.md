---
title: Metodo ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee3a0c27d350dec8e9f3e9448174d978c7d50e81
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775696"
---
# <a name="icorpublishprocessismanaged-method"></a>Metodo ICorPublishProcess::IsManaged
Ottiene un valore che indica se il processo di cui viene fatto riferimento da questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) è noto al codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbManaged`  
 [out] Un puntatore a un valore booleano che indica se il processo con codice gestito. Il valore è `true` se il processo dispone di codice gestito; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Poiché la versione corrente di `ICorPublishProcess` consenta l'accesso solo ai processi con codice gestito, `IsManaged` restituisce sempre `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub.idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
