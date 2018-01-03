---
title: Metodo ICorDebugProcess6::DecodeEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 753dce06d9481165bd2f0f1e49fe3c50fc6b3c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6decodeevent-method"></a>Metodo ICorDebugProcess6::DecodeEvent
Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pRecord`  
 [in] Un puntatore a una matrice di byte da un evento di debug per le eccezioni native che include informazioni relative a un evento di debug gestito.  
  
 `countBytes`  
 [in] Il numero di elementi nella matrice di byte `pRecord`.  
  
 `format`  
 [in] Oggetto [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) membro di enumerazione che specifica il formato dell'evento di debug non gestito.  
  
 `dwFlags`  
 [in] Un campo di bit che dipende dall'architettura di destinazione e che fornisce informazioni aggiuntive relative all'evento di debug. Per i sistemi Windows, può essere un membro del [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumerazione.  
  
 `dwThreadId`  
 [in] L'identificatore del sistema operativo del thread in cui è stata generata l'eccezione.  
  
 `ppEvent`  
 [out] Un puntatore all'indirizzo di un [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) oggetto che rappresenta un evento di debug gestito decodificato.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
