---
title: Interfaccia ICorDebugILFrame4
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: d0b1c31d45efea4892182c43c801112530361994
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213702"
---
# <a name="icordebugilframe4-interface"></a>Interfaccia ICorDebugILFrame4
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio. L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md)|Restituisce un elenco delle variabili locali disponibili nel frame corrente.|  
|[Metodo GetCodeEx](icordebugilframe4-getcodeex-method.md)|Restituisce il codice eseguito da questo stack frame.|  
|[Metodo GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md)|Restituisce il valore di una variabile locale nel frame del linguaggio intermedio.|  
  
## <a name="remarks"></a>Osservazioni  
 Questi metodi offrono funzionalità oltre a quelle fornite dai metodi [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md)e [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) . Ogni metodo include un parametro `flags` che specifica se le variabili locali aggiuntive o il codice definito dalla richiesta ReJIT di un profiler sono visibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
