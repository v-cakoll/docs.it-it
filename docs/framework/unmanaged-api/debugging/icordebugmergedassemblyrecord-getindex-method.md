---
title: Metodo ICorDebugMergedAssemblyRecord::GetIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dac64c785077fc3901e712498e66e11b9c9f3279
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>Metodo ICorDebugMergedAssemblyRecord::GetIndex
Ottiene l'indice del prefisso dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pIndex`  
 [out] Puntatore all'indice del prefisso.  
  
## <a name="remarks"></a>Note  
 L'indice del prefisso viene usato per evitare conflitti di nome nei nomi dei tipi di metadati uniti.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
