---
title: 'Metodo metodo icordebugsymbolprovider:: GetTypeProps'
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: c87d9f6d0a719dae5e532e9c0369a7f9fc03748a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133671"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a>Metodo metodo icordebugsymbolprovider:: GetTypeProps
Restituisce informazioni sulle proprietà di un tipo, ad esempio il numero di firma dei parametri generici, dato un indirizzo RVA (Relative Virtual Address) in un oggetto vtable.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tableRva`  
 [in] Indirizzo RVA (Relative Virtual Address) in un oggetto vtable  
  
 `cbSignature`  
 [in] Dimensione della matrice `signature`. Vedere la sezione Osservazioni.  
  
 `pcbSignature`  
 [out] [out] Puntatore alla dimensione della matrice `signature` restituita.  
  
 `signature`  
 [out] Buffer contenente le firme typespec di tutti i parametri generici.  
  
## <a name="remarks"></a>Note  
 Per ottenere le dimensioni richieste della matrice di `signature` del tipo, impostare l'argomento di `cbSignature` su 0 e `signature` su **null**. Quando il metodo viene restituito, `pcbSignature` conterrà il numero di byte necessari per la matrice `signature`.  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetMethodProps](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)
- [Interfaccia ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
