---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 632e990899346493d5a7df08d293e25b83ed7ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178737"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a>Metodo ICorDebugMergedAssemblyRecord::GetPublicKey
Ottiene la chiave pubblica dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,
   [out] ULONG32 *pcbPublicKey,
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cbPublicKey`  
 [in] Numero massimo di byte nella matrice di `pbPublicKey`.  
  
 `pcbPublicKey`  
 [out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKey`.  
  
 `pbPublicKey`  
 [in] Puntatore a una matrice di byte che contiene la chiave pubblica dell'assembly.  
  
## <a name="remarks"></a>Osservazioni  
  
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
