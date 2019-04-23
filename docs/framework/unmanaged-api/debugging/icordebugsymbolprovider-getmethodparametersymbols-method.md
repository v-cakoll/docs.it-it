---
title: Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98efd1446c88c3a6c004b5a3254c9db835a43804
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197373"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a>Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols
Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nativeRVA`  
 [in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.  
  
 `cRequestedSymbols`  
 [in] Numero di simboli locali richiesti.  
  
 `pcFetchedSymbols`  
 [out] Puntatore al numero di simboli recuperati dal metodo.  
  
 `pcFetchedSymbols`  
 [out] Un puntatore a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matrice che contiene i simboli locali del metodo.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetMethodLocalSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [Interfaccia ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
