---
title: ICorDebugAppDomain3 Interface
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
ms.openlocfilehash: 1aaccb37ec61ed1ba6a7e6e1f508704973117cca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784876"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3 Interface
Fornisce metodi per recuperare informazioni sulle rappresentazioni gestite dei tipi Windows Runtime attualmente caricati in un dominio applicazione. Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md)|Ottiene un enumeratore per tutti i tipi di Windows Runtime memorizzati nella cache.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ottiene un enumeratore per i tipi di Windows Runtime memorizzati nella cache in un dominio applicazione in base ai relativi identificatori di interfaccia.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia deve essere utilizzata da un debugger insieme a una chiamata di valutazione della funzione per `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Quando il metodo recupera gli identificatori di interfaccia supportati da un oggetto Windows Runtime Server, il debugger può utilizzare i metodi definiti in questa interfaccia per eseguirne il mapping ai tipi gestiti che corrispondono a tali interfacce.  
  
 Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
