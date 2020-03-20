---
title: Metodo ICorDebugRegisterSet::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178536"
---
# <a name="icordebugregistersetgetregisters-method"></a>Metodo ICorDebugRegisterSet::GetRegisters
Ottiene il valore di ogni registro (nel computer che sta eseguendo il codice) specificato dalla maschera di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mask`  
 [in] Maschera di bit che specifica quali valori di registro devono essere recuperati. Ogni bit corrisponde a un registro. Se un bit è impostato su uno, viene recuperato il valore del registro; in caso contrario, il valore del registro non viene recuperato.  
  
 `regCount`  
 [in] Numero di valori di registro da recuperare.  
  
 `regBuffer`  
 [fuori] Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve il valore di un registro.  
  
## <a name="remarks"></a>Osservazioni  
 La dimensione della matrice deve essere uguale al numero di bit impostato su uno nella maschera di bit. Il `regCount` parametro specifica il numero di elementi nel buffer che riceveranno i valori di registro. Se `regCount` il valore è troppo piccolo per il numero di registri indicato dalla maschera, i registri con numero più alto verranno troncati dal set. Se `regCount` il valore è troppo grande, gli elementi inutilizzati `regBuffer` non verranno modificati.  
  
 Se la maschera di bit specifica un `GetRegisters` registro non disponibile, restituisce un valore indeterminato per tale registro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
