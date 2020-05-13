---
title: Interfaccia ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208720"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>Interfaccia ICorDebugMergedAssemblyRecord
Fornisce informazioni su un assembly unito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCulture](icordebugmergedassemblyrecord-getculture-method.md)|Ottiene la stringa del nome delle impostazioni cultura dell'assembly.|  
|[Metodo GetIndex](icordebugmergedassemblyrecord-getindex-method.md)|Ottiene l'indice del prefisso dell'assembly.|  
|[Metodo GetPublicKey](icordebugmergedassemblyrecord-getpublickey-method.md)|Ottiene la chiave pubblica dell'assembly.|  
|[Metodo GetPublicKeyToken](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|Ottiene il token di chiave pubblica dell'assembly.|  
|[Metodo GetSimpleName](icordebugmergedassemblyrecord-getsimplename-method.md)|Ottiene il nome semplice dell'assembly.|  
|[Metodo GetVersion](icordebugmergedassemblyrecord-getversion-method.md)|Ottiene le informazioni sulla versione dell'assembly.|  
  
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
