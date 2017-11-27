---
title: Metodo ICorPublishProcess::IsManaged
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 622781a6c1ad5d5efa3bb2d5227c4f5b845bf94e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessismanaged-method"></a>Metodo ICorPublishProcess::IsManaged
Ottiene un valore che indica se il processo a cui fa riferimento questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) è noto al codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbManaged`  
 [out] Un puntatore a un valore booleano che indica se il processo con codice gestito. Il valore è `true` se il processo dispone di codice gestito; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Rispetto alla versione corrente di `ICorPublishProcess` consente l'accesso solo ai processi con codice gestito, `IsManaged` restituisce sempre `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Corpub. idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorPublishProcess (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
