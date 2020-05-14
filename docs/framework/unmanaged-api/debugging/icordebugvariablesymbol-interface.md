---
title: Interfaccia ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 412ecbfc03378947e5a578e163034d104718bc91
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397099"
---
# <a name="icordebugvariablesymbol-interface"></a>Interfaccia ICorDebugVariableSymbol
Recupera le informazioni relative al simbolo di debug per una variabile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetName](icordebugvariablesymbol-getname-method.md)|Ottiene il nome di una variabile.|  
|[Metodo GetSize](icordebugvariablesymbol-getsize-method.md)|Ottiene le dimensioni di una variabile in byte.|  
|[Metodo GetSlotIndex](icordebugvariablesymbol-getslotindex-method.md)|Ottiene l'indice dello slot gestito di una variabile locale.|  
|[Metodo GetValue](icordebugvariablesymbol-getvalue-method.md)|Ottiene il valore di una variabile come matrice di byte.|  
|[Metodo SetValue](icordebugvariablesymbol-setvalue-method.md)|Assegna il valore di una matrice di byte a una variabile.|  
  
## <a name="remarks"></a>Commenti  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
