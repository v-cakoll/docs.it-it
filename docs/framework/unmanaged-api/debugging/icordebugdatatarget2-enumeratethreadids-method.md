---
title: Metodo ICorDebugDataTarget2::EnumerateThreadIDs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c20b7dd1bcbc27edb9be11419b7919250301d488
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a>Metodo ICorDebugDataTarget2::EnumerateThreadIDs
Restituisce un elenco di ID thread attivi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 cThreadIDs  
 [in] Il numero massimo di thread con ID che possono essere restituiti.  
  
 pcThreadIds  
 [out] Un puntatore a `ULONG32` che indica il numero effettivo di ID thread scritti nella matrice `pThreadIds`.  
  
 pThreadIDs  
 Una matrice di identificatori di thread.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md). **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
