---
title: Metodo ICorDebugDataTarget::GetPlatform
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1065c8d710ddbd6088ee0db694a43e098564e707
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750385"
---
# <a name="icordebugdatatargetgetplatform-method"></a>Metodo ICorDebugDataTarget::GetPlatform
Fornisce informazioni sulla piattaforma, tra cui architettura del processore e del sistema operativo, in cui viene eseguito il processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parametri  
 `pTargetPlatform`  
 [out] Un puntatore a un [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumerazione che descrive la piattaforma di destinazione.  
  
## <a name="remarks"></a>Note  
 Il `CorDebugPlatformEnum` valore restituito di enumerazione viene utilizzato per il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia per determinare i dettagli del processo di destinazione, ad esempio le dimensioni del puntatore, layout dello spazio degli indirizzi, register set, formato dell'istruzione, layout di contesto, e convenzioni di chiamata.  
  
 Il `pTargetPlatform` valore può fare riferimento a una piattaforma che viene emulata per la destinazione anziché specificare l'hardware effettivamente in uso. Ad esempio, un processo in esecuzione in di Windows nell'ambiente di Windows (WOW) in una versione a 64 bit del sistema operativo Windows deve usare la `CORDB_PLATFORM_WINDOWS_X86` pari al [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumerazione.  
  
 Questo metodo deve essere completata. In caso contrario, la piattaforma di destinazione è inutilizzabile. Il metodo potrebbe non riuscire per i motivi seguenti:  
  
- La piattaforma che viene emulata per la destinazione è inutilizzabile.  
  
- L'hardware effettivo nella piattaforma di destinazione è inutilizzabile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
