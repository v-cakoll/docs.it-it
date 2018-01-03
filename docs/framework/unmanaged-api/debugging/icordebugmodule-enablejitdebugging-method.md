---
title: Metodo ICorDebugModule::EnableJITDebugging
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableJITDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a699f32d8ec4b2418c6af815c22f35470bede3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>Metodo ICorDebugModule::EnableJITDebugging
Controlla se il compilatore di just-in-time (JIT) consente di mantenere le informazioni di debug per i metodi all'interno del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bTrackJITInfo`  
 [in] Impostare questo valore su `true` per consentire al compilatore JIT di mantenere le informazioni di mapping tra la versione di Microsoft intermediate language (MSIL) e la versione compilata tramite JIT di ogni metodo in questo modulo.  
  
 `bAllowJitOpts`  
 [in] Impostare questo valore su `true` per consentire al compilatore JIT generare il codice con alcune ottimizzazioni JIT specifiche per il debug.  
  
## <a name="remarks"></a>Note  
 Debug JIT è abilitato per impostazione predefinita per tutti i moduli caricati quando è attivo il debugger. A livello di programmazione abilitando o disabilitando le impostazioni di override delle impostazioni globali.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
