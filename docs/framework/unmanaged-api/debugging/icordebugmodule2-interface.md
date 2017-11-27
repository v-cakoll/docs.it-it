---
title: ICorDebugModule2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2
helpviewer_keywords: ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97259783d34babe3f0f229f5d62b3e945c0ac624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2-interface1"></a>ICorDebugModule2 Interface1
Opera come estensione logica dell'interfaccia ICorDebugModule.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ApplyChanges (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Applica le modifiche nei metadati e le modifiche nel codice Microsoft intermediate language (MSIL) per il processo in esecuzione.|  
|[GetJITCompilerFlags (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Ottiene i flag che controllano la compilazione just-in-time (JIT) per questo `ICorDebugModule2`.|  
|[ResolveAssembly (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Consente di risolvere l'assembly a cui fa riferimento il token di metadati specificato.|  
|[SetJITCompilerFlags (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|Imposta i flag che controllano la compilazione JIT per questa `ICorDebugModule2`.|  
|[SetJMCStatus (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Imposta lo stato JMC Just My Code () di tutti i metodi di tutte le classi in questo `ICorDebugModule2` sul valore specificato, ad eccezione di quelli di `pTokens` matrice, che vengono impostati sul valore opposto.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
