---
title: Interfaccia ICorDebugThread3
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: dc556dfb59e999ed9b7fc5f35c603dc26c35f314
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378713"
---
# <a name="icordebugthread3-interface"></a>Interfaccia ICorDebugThread3
Fornisce il punto di ingresso per [ICorDebugStackWalk](icordebugstackwalk-interface.md) e le interfacce corrispondenti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateStackWalk](icordebugthread3-createstackwalk-method.md)|Crea un oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) per il thread il cui stack si vuole rimuovere.|  
|[Metodo GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md)|Restituisce una matrice di frame interni (oggetti[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) nello stack.|  
  
## <a name="remarks"></a>Osservazioni  
 `ICorDebugThread3`è un'estensione logica dell'interfaccia ICorDebugThread.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
