---
title: Metodo ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 7800630be0ed9afb321d607046be308088781388
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976447"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a>Metodo ICorDebugDataTarget2::GetSymbolProviderForImage
Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `imageBaseAddress`  
 in Valore [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) che rappresenta l'indirizzo di base di un modulo.  
  
 `ppSymProvider`  
 out Puntatore all'indirizzo di un oggetto [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) .  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
