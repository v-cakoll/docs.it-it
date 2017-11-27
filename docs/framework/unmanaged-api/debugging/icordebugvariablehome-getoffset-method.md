---
title: Metodo ICorDebugVariableHome::GetOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ddedc83e4e51cf12a3f8a0504d90bda7f944a6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a>Metodo ICorDebugVariableHome::GetOffset
Ottiene l'offset del Registro di base per una variabile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pOffset`  
 [out] L'offset del Registro di base.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce i valori seguenti:  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`S_OK`|La variabile è in una posizione di memoria relativo al registro.|  
|`E_FAIL`|La variabile non è presente in una posizione di memoria relativo al registro.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
