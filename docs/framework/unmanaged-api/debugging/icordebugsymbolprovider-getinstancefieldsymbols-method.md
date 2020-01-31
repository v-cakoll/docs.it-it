---
title: Metodo ICorDebugSymbolProvider::GetInstanceFieldSymbols
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9c55ce4d36681e173047cfb51515a74899c5a9fe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791639"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a>Metodo ICorDebugSymbolProvider::GetInstanceFieldSymbols
Ottiene i simboli dei campi di istanza che corrispondono a una firma typespec.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cbSignature`  
 [in] Numero di byte nella matrice di `typeSig`.  
  
 `typeSig`  
 [in] Matrice di byte che contiene la firma `typespec`.  
  
 `cRequestedSymbols`  
 [in] Numero di simboli richiesti.  
  
 `pcFetchedSymbols`  
 [out] Puntatore al numero di simboli recuperati dal metodo.  
  
 `pSymbols`  
 out Puntatore a una matrice [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) che contiene i simboli dei campi di istanza richiesti.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetStaticFieldSymbols](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [Interfaccia ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
