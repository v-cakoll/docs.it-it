---
title: Metodo ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36cf8647b3caafeaae2db3c2fd53471496e922fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109539"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>Metodo ICorDebugMergedAssemblyRecord::GetVersion
Ottiene le informazioni sulla versione dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pMajor`  
 [out] Puntatore al numero di versione principale.  
  
 `pMinor`  
 [out] Puntatore al numero di versione secondario.  
  
 `pBuild`  
 [out] Puntatore al numero di build.  
  
 `pRevision`  
 [out] Puntatore al numero di revisione.  
  
## <a name="remarks"></a>Note  
 Per informazioni sui numeri di versione degli assembly, vedere l'argomento relativo alla classe <xref:System.Version>.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
