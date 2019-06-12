---
title: Interfaccia ICorDebugAppDomain3
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025888"
---
# <a name="icordebugappdomain3-interface"></a>Interfaccia ICorDebugAppDomain3
Fornisce metodi per recuperare informazioni sulle rappresentazioni di tipi Windows Runtime attualmente caricati in un dominio dell'applicazione gestite. Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Ottiene un enumeratore per tutti i tipi Windows Runtime memorizzato nella cache.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ottiene un enumeratore per i tipi Windows Runtime memorizzato nella cache in un dominio di applicazione basato su identificatori relativi interfaccia.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia deve essere usata da un debugger in combinazione con una chiamata di valutazione di funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Quando il metodo recupera gli identificatori di interfaccia supportati da un oggetto server di Windows Runtime, il debugger potrebbe usare i metodi definiti in questa interfaccia per eseguirne il mapping a tipi gestiti che corrispondono a tali interfacce.  
  
 Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
