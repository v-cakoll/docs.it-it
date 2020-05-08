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
ms.openlocfilehash: 3df35d52a4e5209b282ccef653b065bdcf1f8fe4
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976538"
---
# <a name="icordebugdatatargetgetplatform-method"></a>Metodo ICorDebugDataTarget::GetPlatform
Fornisce informazioni sulla piattaforma, tra cui l'architettura del processore e il sistema operativo in cui è in esecuzione il processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>Parametri  
 `pTargetPlatform`  
 out Puntatore a un'enumerazione [CorDebugPlatformEnum](cordebugplatform-enumeration.md) che descrive la piattaforma di destinazione.  
  
## <a name="remarks"></a>Osservazioni  
 Il `CorDebugPlatformEnum` valore restituito dell'enumerazione viene utilizzato dall'interfaccia [ICorDebug](icordebug-interface.md) per determinare i dettagli del processo di destinazione, ad esempio le dimensioni del puntatore, il layout dello spazio degli indirizzi, il set di registri, il formato di istruzione, il layout del contesto e le convenzioni di chiamata.  
  
 Il `pTargetPlatform` valore può fare riferimento a una piattaforma da emulare per la destinazione invece di specificare l'hardware effettivo in uso. Ad esempio, un processo in esecuzione nell'ambiente Windows in Windows (WOW) in un'edizione a 64 bit del sistema operativo Windows deve usare il `CORDB_PLATFORM_WINDOWS_X86` valore dell'enumerazione [CorDebugPlatformEnum](cordebugplatform-enumeration.md) .  
  
 Questo metodo deve avere esito positivo. In caso di errore, la piattaforma di destinazione è inutilizzabile. Il metodo può non riuscire per i motivi seguenti:  
  
- La piattaforma da emulare per la destinazione è inutilizzabile.  
  
- L'hardware effettivo nella piattaforma di destinazione è inutilizzabile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
