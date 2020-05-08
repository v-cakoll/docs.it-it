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
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895179"
---
# <a name="icordebugappdomain-interface"></a>Interfaccia ICorDebugAppDomain

Fornisce metodi per il debug di domini applicazione. Questa interfaccia è una sottoclasse di ICorDebugController.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Attach](icordebugappdomain-attach-method.md)|Connette il debugger al dominio applicazione.|  
|[Metodo EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|Ottiene un enumeratore per gli assembly nel dominio dell'applicazione.|  
|[Metodo EnumerateBreakpoints](icordebugappdomain-enumeratebreakpoints-method.md)|Ottiene un enumeratore per tutti i punti di interruzione attivi nel dominio applicazione.|  
|[Metodo EnumerateSteppers](icordebugappdomain-enumeratesteppers-method.md)|Ottiene un enumeratore per tutti i Stepper attivi nel dominio applicazione.|  
|[Metodo GetId](icordebugappdomain-getid-method.md)|Ottiene l'ID univoco del dominio dell'applicazione.|  
|[Metodo GetModuleFromMetaDataInterface](icordebugappdomain-getmodulefrommetadatainterface-method.md)|Ottiene l'oggetto ICorDebugModule con l'interfaccia dei metadati specificata.|  
|[Metodo GetName](icordebugappdomain-getname-method.md)|Ottiene il nome del dominio dell'applicazione.|  
|[Metodo GetObject](icordebugappdomain-getobject-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione Common Language Runtime (CLR).|  
|[Metodo GetProcess](icordebugappdomain-getprocess-method.md)|Ottiene il processo che contiene il dominio applicazione.|  
|[Metodo IsAttached](icordebugappdomain-isattached-method.md)|Determina se il debugger è collegato al dominio applicazione.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
