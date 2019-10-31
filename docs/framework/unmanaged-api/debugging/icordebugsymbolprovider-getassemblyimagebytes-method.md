---
title: 'Metodo metodo icordebugsymbolprovider:: GetAssemblyImageBytes'
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 3184ba116704df8945b53766e62435a4252eaa11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138930"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a>Metodo metodo icordebugsymbolprovider:: GetAssemblyImageBytes
Legge i dati da un assembly sottoposto a merge tramite un indirizzo RVA (Relative Virtual Address) specificato nell'assembly sottoposto a merge.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `rva`  
 [in] Indirizzo RVA (Relative Virtual Address) in un assembly sottoposto a merge.  
  
 `length`  
 Numero di byte da leggere dall'assembly sottoposto a merge.  
  
 `ppMemoryBuffer`  
 Puntatore all'indirizzo di un oggetto [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) che contiene informazioni sul buffer di memoria con i metadati dell'assembly Uniti.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
