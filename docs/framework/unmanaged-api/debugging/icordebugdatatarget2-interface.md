---
title: Interfaccia ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 1c598d23cac77e50cf302e6936b88b5eb6e558c2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976434"
---
# <a name="icordebugdatatarget2-interface"></a>Interfaccia ICorDebugDataTarget2
Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateVirtualUnwinder](icordebugdatatarget2-createvirtualunwinder-method.md)|Crea un nuovo agente di rimozione dello stack che avvia la rimozione da un contesto iniziale (non necessariamente la foglia di un thread).|  
|[Metodo EnumerateThreadIDs](icordebugdatatarget2-enumeratethreadids-method.md)|Restituisce un elenco di ID thread attivi.|  
|[Metodo GetImageFromPointer](icordebugdatatarget2-getimagefrompointer-method.md)|Restituisce l'indirizzo di base e le dimensioni del modulo da un indirizzo contenuto nel modulo.|  
|[Metodo GetImageLocation](icordebugdatatarget2-getimagelocation-method.md)|Restituisce il percorso di un modulo dall'indirizzo di base del modulo.|  
|[Metodo GetSymbolProviderForImage](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Restituisce il provider di simboli per un modulo dall'indirizzo di base del modulo.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
