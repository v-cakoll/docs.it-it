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
ms.openlocfilehash: 40de06d47654337542d2c80dc325f8201335312a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379149"
---
# <a name="icordebugregistersetgetregisters-method"></a>Metodo ICorDebugRegisterSet::GetRegisters
Ottiene il valore di ogni registro (nel computer in cui è attualmente in esecuzione il codice) specificato dalla maschera di bit.  
  
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
 in Maschera di bit che specifica i valori di registro da recuperare. Ogni bit corrisponde a un registro. Se un bit è impostato su uno, il valore del registro viene recuperato. in caso contrario, il valore del registro non viene recuperato.  
  
 `regCount`  
 in Numero di valori di registro da recuperare.  
  
 `regBuffer`  
 out Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve un valore di un registro.  
  
## <a name="remarks"></a>Osservazioni  
 La dimensione della matrice deve essere uguale al numero di bit impostato su uno nella maschera di bit. Il `regCount` parametro specifica il numero di elementi nel buffer che riceveranno i valori del registro. Se il `regCount` valore è troppo piccolo per il numero di registri indicato dalla maschera, i registri con numero più elevato verranno troncati dal set. Se il `regCount` valore è troppo grande, gli elementi inutilizzati non `regBuffer` verranno modificati.  
  
 Se la maschera di bit specifica un registro non disponibile, `GetRegisters` restituisce un valore indeterminato per tale registro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
