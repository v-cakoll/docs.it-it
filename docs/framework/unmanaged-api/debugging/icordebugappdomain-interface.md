---
title: ICorDebugAppDomain Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain
helpviewer_keywords: ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19cf38920ed818dfbba9cd83bd64fdc408281e0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain Interface1
Fornisce metodi per il debug di domini applicazione. Questa interfaccia è una sottoclasse di ICorDebugController.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Attach (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Collega il debugger per il dominio dell'applicazione.|  
|[EnumerateAssemblies (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.|  
|[EnumerateBreakpoints (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio dell'applicazione.|  
|[EnumerateSteppers (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Ottiene un enumeratore per tutti i gestori di istruzioni attive nel dominio dell'applicazione.|  
|[GetID (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Ottiene l'ID univoco del dominio dell'applicazione.|  
|[GetModuleFromMetaDataInterface (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Ottiene l'oggetto ICorDebugModule con l'interfaccia di metadati specificato.|  
|[GetName (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Ottiene il nome del dominio dell'applicazione.|  
|[GetObject (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Ottiene un puntatore a interfaccia per il dominio di applicazione di common language runtime (CLR).|  
|[GetProcess (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Ottiene il processo che contiene il dominio dell'applicazione.|  
|[IsAttached (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Determina se il debugger è collegato al dominio applicazione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
