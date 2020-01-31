---
title: Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: a940077e50ff251111ca6eedaee49401775644d3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791590"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a>Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols
Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 out Puntatore a una matrice [Metodo icordebugvariablesymbol](icordebugvariablesymbol-interface.md) che contiene i simboli locali del metodo.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetMethodLocalSymbols](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [Interfaccia ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
