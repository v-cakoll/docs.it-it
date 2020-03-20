---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: 79df5c3e8b07879a26272f595664abab011101bd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178728"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
Ottiene il token di chiave pubblica dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,
   [out] ULONG32 *pcbPublicKeyToken,
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cbPublicKeyToken`  
 [in] Numero massimo di byte nella matrice di `pbPublicKeyToken`.  
  
 `pcbPublicKeyToken`  
 [out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKeyToken`.  
  
 `pbPublicKeyToken`  
 [out] Puntatore a una matrice di byte che contiene il token di chiave pubblica dell'assembly.  
  
## <a name="remarks"></a>Osservazioni  
 Il token di chiave pubblica di un assembly corrisponde agli ultimi otto byte di un hash SHA1 della relativa chiave pubblica.  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
