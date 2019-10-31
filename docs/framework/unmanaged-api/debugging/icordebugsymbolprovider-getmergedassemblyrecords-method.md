---
title: 'Metodo metodo icordebugsymbolprovider:: GetMergedAssemblyRecords'
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 6faf8960c06488c8fff5a076aae375529e1d0260
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138870"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a>Metodo metodo icordebugsymbolprovider:: GetMergedAssemblyRecords
Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cRequestedRecords`  
 [in] Numero di record dei simboli richiesti.  
  
 `pcFetchedRecords`  
 [out] Puntatore al numero di record dei simboli recuperati dal metodo.  
  
 `pRecords`  
 Puntatore a una matrice di oggetti [Metodo icordebugmergedassemblyrecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) .  
  
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
