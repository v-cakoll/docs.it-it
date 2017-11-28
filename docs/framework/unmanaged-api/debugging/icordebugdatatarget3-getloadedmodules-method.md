---
title: Metodo ICorDebugDataTarget3::GetLoadedModules
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc4820d2c71830b297ed690c440c90cfff1f9601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget3](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
