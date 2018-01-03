---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1871e6060303ad496e4edb7bed47b9d91ecf71f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
Ottiene il token di chiave pubblica dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cbPublicKeyToken`  
 [in] Numero massimo di byte nella matrice di `pbPublicKeyToken`.  
  
 `pcbPublicKeyToken`  
 [out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKeyToken`.  
  
 `pbPublicKeyToken`  
 [out] Puntatore a una matrice di byte che contiene il token di chiave pubblica dell'assembly.  
  
## <a name="remarks"></a>Note  
 Il token di chiave pubblica di un assembly corrisponde agli ultimi otto byte di un hash SHA1 della relativa chiave pubblica.  
  
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
