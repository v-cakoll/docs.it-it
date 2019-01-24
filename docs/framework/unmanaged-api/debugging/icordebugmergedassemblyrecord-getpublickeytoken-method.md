---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f77871c8547f250d4b46c11c1a0be25b6ef68a88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581943"
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
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
