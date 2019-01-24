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
ms.openlocfilehash: ade4c88f4431dd6db636ea2581bdb936ac8d8e5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538011"
---
# <a name="icordebugappdomain3-interface"></a>Interfaccia ICorDebugAppDomain3
Fornisce metodi per recuperare informazioni sulle rappresentazioni di gestito di [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati in un dominio dell'applicazione. Questa interfaccia è un'estensione delle interfacce ICorDebugAppDomain e ICorDebugAppDomain2.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Ottiene un enumeratore per tutte le cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ottiene un enumeratore per memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi in un dominio dell'applicazione basati sui rispettivi identificatori di interfaccia.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia deve essere usata da un debugger in combinazione con una chiamata di valutazione di funzione a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Quando il metodo recupera gli identificatori di interfaccia supportati da un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server dell'oggetto, il debugger potrebbe usare i metodi definiti in questa interfaccia per eseguirne il mapping a tipi gestiti che corrispondono a tali interfacce.  
  
 Per recuperare un'istanza di questa interfaccia, eseguire `QueryInterface` in un'istanza dell'interfaccia ICorDebugAppDomain o ICorDebugAppDomain2.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
