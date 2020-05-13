---
title: Interfaccia ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: a7b0608e85411844828cebea34c0ce5ef5b1bd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379390"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>Interfaccia ICorDebugRuntimeUnwindableFrame
Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.  
  
## <a name="remarks"></a>Osservazioni  
 `ICorDebugRuntimeUnwindableFrame`è una versione specializzata dell'interfaccia ICorDebugFrame. Viene usato da metodi non gestiti che richiedono al runtime di rimuovere un frame nello stack corrente. Le convenzioni di rimozione esistenti non funzionano perché non utilizzano codice compilato tramite JIT. Quando il debugger rileva un frame non ricaricabile, deve usare il metodo [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) per rimuoverlo, ma deve eseguire un controllo. Quando il debugger riceve un oggetto `ICorDebugRuntimeUnwindableFrame` , può chiamare il metodo [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) per recuperare il contesto del frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
