---
title: Interfaccia ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: 611091d39da6d7f646457457f20ce1eaf37db361
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213205"
---
# <a name="icordebugfunction2-interface"></a>Interfaccia ICorDebugFunction2

Estende logicamente l'interfaccia ICorDebugFunction per fornire supporto per Just My Code il debug step-through, che ignora il codice non utente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateNativeCode](icordebugfunction2-enumeratenativecode-method.md)|(Non ancora implementato). Ottiene un puntatore a interfaccia a un ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.|  
|[Metodo GetJMCStatus](icordebugfunction2-getjmcstatus-method.md)|Ottiene un valore che indica se questa funzione è contrassegnata come codice utente.|  
|[Metodo GetVersionNumber](icordebugfunction2-getversionnumber-method.md)|Ottiene la versione di modifica e continuazione di questa funzione.|  
|[Metodo SetJMCStatus](icordebugfunction2-setjmcstatus-method.md)|Contrassegna questa funzione per Just My Code esecuzione di un'istruzione.|  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
