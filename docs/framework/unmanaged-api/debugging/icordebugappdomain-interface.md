---
title: Interfaccia ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 9abcb765357a0f305ae5acae77a4a13b07a003a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134677"
---
# <a name="icordebugappdomain-interface"></a>Interfaccia ICorDebugAppDomain

Fornisce metodi per il debug di domini applicazione. Questa interfaccia è una sottoclasse di ICorDebugController.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Attach](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Connette il debugger al dominio applicazione.|  
|[Metodo EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.|  
|[Metodo EnumerateBreakpoints](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.|  
|[Metodo EnumerateSteppers](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Ottiene un enumeratore per tutti i Stepper attivi nel dominio applicazione.|  
|[Metodo GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Ottiene l'ID univoco del dominio dell'applicazione.|  
|[Metodo GetModuleFromMetaDataInterface](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Ottiene l'oggetto ICorDebugModule con l'interfaccia dei metadati specificata.|  
|[Metodo GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Ottiene il nome del dominio dell'applicazione.|  
|[Metodo GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).|  
|[Metodo GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Ottiene il processo che contiene il dominio applicazione.|  
|[Metodo IsAttached](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Determina se il debugger è collegato al dominio applicazione.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
