---
title: Metodo ICorDebugRegisterSet2::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2dc1064656f3493db78d858cf1e86db0cb83d6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782863"
---
# <a name="icordebugregisterset2getregisters-method"></a>Metodo ICorDebugRegisterSet2::GetRegisters
Ottiene il valore di ogni registro (per la piattaforma su cui è attualmente in esecuzione codice) specificato dalla maschera di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `maskCount`  
 [in] Le dimensioni, in byte, del `mask` matrice.  
  
 `mask`  
 [in] Matrice di byte, ogni bit che corrisponde a un registro. Se il bit è 1, verrà recuperato il corrispondente valore del registro.  
  
 `regCount`  
 [in] Il numero di valori di registro da recuperare.  
  
 `regBuffer`  
 [out] Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve il valore di un registro.  
  
## <a name="remarks"></a>Note  
 Il `GetRegisters` metodo restituisce una matrice di valori dai registri che vengono specificati dalla maschera. La matrice non contiene valori dei registri la cui maschera bit non è impostato. Di conseguenza, le dimensioni del `regBuffer` matrice deve essere uguale al numero di 1 nella maschera. Se il valore di `regCount` è troppo piccolo per il numero di registri indicati dalla maschera, i valori dei registri numerati superiore verrà troncato dal set. Se `regCount` è troppo grande, inutilizzata `regBuffer` elementi saranno non modificati.  
  
 Se un registro non disponibile viene indicato dalla maschera, verrà restituito un valore indeterminato per tale registro.  
  
 Il `ICorDebugRegisterSet2::GetRegisters` metodo è necessario per le piattaforme che hanno più di 64 registri. Ad esempio, IA64 è 128 registri di utilizzo generico e 128 registri a virgola mobile, pertanto è necessario più di 64-bit nella maschera di bit.  
  
 Se non è più di 64 registri, come nel caso in piattaforme, ad esempio x86, il `GetRegisters` metodo converte semplicemente i byte nel `mask` matrice di byte in un `ULONG64` e quindi chiama il [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) metodo, che utilizza il `ULONG64` maschera.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
