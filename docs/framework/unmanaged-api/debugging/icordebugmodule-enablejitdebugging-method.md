---
title: Metodo ICorDebugModule::EnableJITDebugging
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 642c4fd600d10ef89a08aa32bef5c8e7455552c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937176"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>Metodo ICorDebugModule::EnableJITDebugging
Controlla se il compilatore JIT just-in-time mantiene le informazioni di debug per i metodi all'interno del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bTrackJITInfo`  
 [in] Impostare questo valore su `true` per consentire al compilatore JIT conservare le informazioni di mapping tra la versione di Microsoft intermediate language (MSIL) e la versione di ogni metodo in questo modulo compilato tramite JIT.  
  
 `bAllowJitOpts`  
 [in] Impostare questo valore su `true` per consentire al compilatore JIT generare il codice con alcune ottimizzazioni JIT specifiche per il debug.  
  
## <a name="remarks"></a>Note  
 Debug JIT è abilitato per impostazione predefinita per tutti i moduli che vengono caricati quando il debugger è attivo. A livello di programmazione abilitando o disabilitando le impostazioni di override delle impostazioni globali.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
