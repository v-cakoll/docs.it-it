---
title: Metodo ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: cc5a2e1de79d6ba04ff3bf2bf86e0cb7ce9a5c0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788385"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>Metodo ICorDebugManagedCallback::LoadClass
Notifica al debugger che è stata caricata una classe.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata caricata la classe.  
  
 `c`  
 in Puntatore a un oggetto ICorDebugClass che rappresenta la classe.  
  
## <a name="remarks"></a>Note  
 Questo callback si verifica solo se è stato abilitato il caricamento della classe per il modulo che contiene la classe. Il caricamento delle classi è sempre abilitato per i moduli dinamici.  
  
 Il callback `LoadClass` fornisce un tempo appropriato per associare i punti di interruzione alle classi appena generate nei moduli dinamici.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo UnloadClass](icordebugmanagedcallback-unloadclass-method.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
