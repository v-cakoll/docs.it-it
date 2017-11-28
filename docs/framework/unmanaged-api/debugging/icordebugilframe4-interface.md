---
title: Interfaccia ICorDebugILFrame4
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a>Interfaccia ICorDebugILFrame4
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio. L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|Restituisce un elenco delle variabili locali disponibili nel frame corrente.|  
|[Metodo GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|Restituisce il codice eseguito da questo stack frame.|  
|[Metodo GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|Restituisce il valore di una variabile locale nel frame del linguaggio intermedio.|  
  
## <a name="remarks"></a>Note  
 Questi metodi offrono funzionalità aggiuntive oltre a quelle fornite dal [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), e [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) metodi. Ogni metodo include un parametro `flags` che specifica se le variabili locali aggiuntive o il codice definito dalla richiesta ReJIT di un profiler sono visibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
