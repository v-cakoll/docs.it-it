---
title: Metodo ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c51ce8ff76e0fc1588cdd136de83b77dcab0f10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>Metodo ICorDebugDataTarget3::GetLoadedModules
Ottiene un elenco dei moduli caricati fino a questo momento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cRequestedModules`  
 [in] Numero di moduli per i quali sono richieste informazioni.  
  
 `pcFetchedModules`  
 [out] Puntatore al numero di moduli sui quali sono state restituite informazioni.  
  
 `pLoadedModules`  
 [out] Un puntatore a una matrice di [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) gli oggetti che forniscono informazioni sui moduli caricati.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget3](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
