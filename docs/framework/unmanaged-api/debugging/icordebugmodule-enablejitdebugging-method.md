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
ms.openlocfilehash: bdf027f94c8416d052cb807d04be76a39868ccf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212932"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>Metodo ICorDebugModule::EnableJITDebugging
Controlla se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bTrackJITInfo`  
 in Impostare questo valore su `true` per consentire al compilatore JIT di mantenere le informazioni di mapping tra la versione Microsoft Intermediate Language (MSIL) e la versione compilata tramite JIT di ogni metodo in questo modulo.  
  
 `bAllowJitOpts`  
 in Impostare questo valore su `true` per consentire al compilatore JIT di generare codice con determinate ottimizzazioni specifiche di JIT per il debug.  
  
## <a name="remarks"></a>Osservazioni  
 Il debug JIT è abilitato per impostazione predefinita per tutti i moduli caricati quando il debugger è attivo. L'abilitazione o la disabilitazione delle impostazioni a livello di codice sostituisce le impostazioni globali.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
