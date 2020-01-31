---
title: Interfaccia ICorDebugAppDomain2
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: 6f9bcec66ff613d19c1198ac9849ca28c978f537
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788949"
---
# <a name="icordebugappdomain2-interface"></a>Interfaccia ICorDebugAppDomain2

Fornisce metodi per lavorare con matrici, puntatori, puntatori a funzione e tipi di riferimento. Questa interfaccia è un'estensione dell'interfaccia ICorDebugAppDomain.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetArrayOrPointerType](icordebugappdomain2-getarrayorpointertype-method.md)|Ottiene una matrice del tipo specificato o un puntatore o un riferimento al tipo specificato.|  
|[GetFunctionPointerType](icordebugappdomain2-getfunctionpointertype-method.md)|Ottiene un puntatore a una funzione con una firma specificata.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
