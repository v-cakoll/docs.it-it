---
title: Metodo ICorDebugSymbolProvider::GetMethodProps
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f52d20b9cb717d72d660bb19a0474c3e5b293ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>Metodo ICorDebugSymbolProvider::GetMethodProps
Restituisce informazioni sulle proprietà del metodo, ad esempio il token di metadati del metodo e informazioni sui relativi parametri generici, da un indirizzo RVA (Relative Virtual Address) fornito in tale metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `codeRVA`  
 [in] Indirizzo virtuale relativo del metodo sul quale recuperare informazioni.  
  
 `pMethodToken`  
 [out] Puntatore al token di metadati del metodo.  
  
 `pcGenericParams`  
 [out] Puntatore al numero di parametri generici associati al metodo.  
  
 `cbSignature`  
 [in] Dimensione della matrice `signature`. Vedere la sezione Osservazioni.  
  
 `pcbSignature`  
 [out] Puntatore alla dimensione della matrice `signature` restituita.  
  
 `signature`  
 [out] Buffer contenente le firme typespec di tutti i parametri generici.  
  
## <a name="remarks"></a>Note  
 Per ottenere la dimensione necessaria del metodo `signature` matrice, impostare il `cbSignature` argomento su 0 e `signature` a **null**. Quando il metodo viene restituito, `pcbSignature` conterrà il numero di byte necessari per la matrice `signature`.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetTypeProps](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)  
 [Interfaccia ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
