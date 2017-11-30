---
title: Metodo ICorDebugVariableSymbol::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aff18efb6781aee5b6a148fcd59863a2ce657023
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetname-method"></a>Metodo ICorDebugVariableSymbol::GetName
Ottiene il nome di una variabile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cchName`  
 [in] Numero di caratteri nel buffer `szName`.  
  
 `pcchName`  
 [out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.  
  
 `szName`  
 Puntatore a una matrice di caratteri che contiene il nome della variabile.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
