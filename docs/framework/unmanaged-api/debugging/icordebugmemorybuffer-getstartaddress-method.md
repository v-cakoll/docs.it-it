---
title: Metodo ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212347"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>Metodo ICorDebugMemoryBuffer::GetStartAddress
Ottiene l'indirizzo iniziale del buffer di memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 [out] Puntatore all'indirizzo iniziale del buffer di memoria.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!WARNING]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
