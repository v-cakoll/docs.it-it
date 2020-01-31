---
title: Interfaccia ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 32774aacecf3e56510bc6f0670538a44fde794c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792981"
---
# <a name="icordebugmodule2-interface"></a>Interfaccia ICorDebugModule2

Funge da estensione logica per l'interfaccia ICorDebugModule.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ApplyChanges](icordebugmodule2-applychanges-method.md)|Applica le modifiche nei metadati e le modifiche nel codice MSIL (Microsoft Intermediate Language) al processo in esecuzione.|  
|[Metodo GetJITCompilerFlags](icordebugmodule2-getjitcompilerflags-method.md)|Ottiene i flag che controllano la compilazione JIT (just-in-Time) per questo `ICorDebugModule2`.|  
|[Metodo ResolveAssembly](icordebugmodule2-resolveassembly-method.md)|Risolve l'assembly a cui fa riferimento il token di metadati specificato.|  
|[Metodo SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md)|Imposta i flag che controllano la compilazione JIT per questo `ICorDebugModule2`.|  
|[Metodo SetJMCStatus](icordebugmodule2-setjmcstatus-method.md)|Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo `ICorDebugModule2` sul valore specificato, ad eccezione di quelli nella matrice `pTokens`, che imposta sul valore opposto.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
