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
ms.openlocfilehash: aca83a66520531074f376a47a7f2994cda237f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423234"
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
  
#### <a name="parameters"></a>Parametri  
 `maskCount`  
 [in] Le dimensioni, in byte, del `mask` matrice.  
  
 `mask`  
 [in] Matrice di byte, ogni bit che corrisponde a un registro. Se il bit è 1, verrà recuperato il valore del registro corrispondenti.  
  
 `regCount`  
 [in] Il numero di valori del registro da recuperare.  
  
 `regBuffer`  
 [out] Matrice di `CORDB_REGISTER` oggetti, ognuno dei quali riceve il valore di un registro.  
  
## <a name="remarks"></a>Note  
 Il `GetRegisters` metodo restituisce una matrice di valori dai registri specificati dalla maschera. La matrice non contiene valori dei registri con maschera bit non è impostato. Di conseguenza, le dimensioni del `regBuffer` matrice deve essere uguale al numero di 1 nella maschera. Se il valore di `regCount` è troppo piccolo per il numero di registri indicato dalla maschera, i valori dei registri con numero maggiore verrà troncato dal set. Se `regCount` è troppo grande, inutilizzata `regBuffer` gli elementi verranno modificati.  
  
 Se un registro non disponibile viene indicato dalla maschera, verrà restituito un valore indeterminato per tale registro.  
  
 Il `ICorDebugRegisterSet2::GetRegisters` metodo è necessario per le piattaforme che hanno più di 64 registri. Ad esempio, IA64 ha 128 registri di uso generale e 128 registri a virgola mobile, pertanto è necessario più di 64-bit nella maschera di bit.  
  
 Se non si dispone più di 64 registri, come nel caso di piattaforme, ad esempio x86, il `GetRegisters` metodo converte semplicemente i byte di `mask` matrice di byte in un `ULONG64` e quindi chiama il [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) metodo, che accetta il `ULONG64` mask.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
