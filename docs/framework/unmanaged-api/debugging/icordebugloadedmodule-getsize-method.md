---
title: Metodo ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788459"
---
# <a name="icordebugloadedmodulegetsize-method"></a>Metodo ICorDebugLoadedModule::GetSize
Ottiene le dimensioni, in byte, del modulo caricato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pcBytes`  
 [out] Puntatore al numero di byte nel modulo caricato.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugLoadedModule](icordebugloadedmodule-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
