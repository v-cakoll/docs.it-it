---
title: Metodo ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fd66ee28ca276aaa31e1e92a42d0fd88ff00d89
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654960"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>Metodo ICorDebugMergedAssemblyRecord::GetCulture
Ottiene la stringa del nome delle impostazioni cultura dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cchCulture`  
 [in] Numero di caratteri nel buffer `szCulture`.  
  
 `pcchCulture`  
 [out] Numero di byte effettivamente scritti nel buffer `szCulture`.  
  
 `szCulture`  
 [out] Matrice di caratteri che contiene il nome delle impostazioni cultura.  
  
## <a name="remarks"></a>Note  
 Il nome delle impostazioni cultura è rappresentato da una stringa univoca che identifica delle impostazioni cultura, ad esempio "en-US" per le impostazioni cultura inglese (Stati Uniti) o "neutral" per impostazioni cultura non associate ad alcun paese.  
  
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
