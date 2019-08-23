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
ms.openlocfilehash: c3676cb32ceaf6f241672751f0feafbd3cb83e05
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968868"
---
# <a name="icordebugappdomain3-interface"></a>Interfaccia ICorDebugAppDomain3
Fornisce metodi per recuperare informazioni sulle rappresentazioni gestite dei tipi Windows Runtime attualmente caricati in un dominio applicazione. Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Ottiene un enumeratore per tutti i tipi di Windows Runtime memorizzati nella cache.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ottiene un enumeratore per i tipi di Windows Runtime memorizzati nella cache in un dominio applicazione in base ai relativi identificatori di interfaccia.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia deve essere utilizzata da un debugger insieme a una chiamata di valutazione della funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Quando il metodo recupera gli identificatori di interfaccia supportati da un oggetto Windows Runtime Server, il debugger può utilizzare i metodi definiti in questa interfaccia per eseguirne il mapping ai tipi gestiti che corrispondono a tali interfacce.  
  
 Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Windows Runtime  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
