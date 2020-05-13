---
title: Metodo ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 7c163311f9ce8f3d98ce72f45165a5e517c6c0aa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205507"
---
# <a name="icordebugprocess6decodeevent-method"></a>Metodo ICorDebugProcess6::DecodeEvent
Decodifica gli eventi di debug gestiti incapsulati nel payload di eventi di debug per le eccezioni native appositamente predisposte.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pRecord`  
 [in] Un puntatore a una matrice di byte da un evento di debug per le eccezioni native che include informazioni relative a un evento di debug gestito.  
  
 `countBytes`  
 [in] Il numero di elementi nella matrice di byte `pRecord`.  
  
 `format`  
 in Membro di enumerazione [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) che specifica il formato dell'evento di debug non gestito.  
  
 `dwFlags`  
 [in] Un campo di bit che dipende dall'architettura di destinazione e che fornisce informazioni aggiuntive relative all'evento di debug. Per i sistemi Windows, può essere un membro dell'enumerazione [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) .  
  
 `dwThreadId`  
 [in] L'identificatore del sistema operativo del thread in cui è stata generata l'eccezione.  
  
 `ppEvent`  
 out Puntatore all'indirizzo di un oggetto [ICorDebugDebugEvent](icordebugdebugevent-interface.md) che rappresenta un evento di debug gestito decodificato.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
