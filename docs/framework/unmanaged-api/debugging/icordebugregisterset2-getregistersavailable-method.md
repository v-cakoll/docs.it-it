---
title: Metodo ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378215"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Metodo ICorDebugRegisterSet2::GetRegistersAvailable
Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `numChunks`  
 [in] Dimensione della matrice `availableRegChunks`.  
  
 `availableRegChunks`  
 out Matrice di byte, ogni bit corrispondente a un registro. Se è disponibile un registro, viene impostato il bit corrispondente del registro.  
  
## <a name="remarks"></a>Osservazioni  
 I valori dell'enumerazione CorDebugRegister specificano i registri di microprocessori diversi. I cinque bit superiori di ogni valore sono l'indice nella `availableRegChunks` matrice di byte. I tre bit inferiori di ogni valore identificano la posizione del bit all'interno del byte indicizzato. Dato un `CorDebugRegister` valore che specifica un registro particolare, la posizione del registro nella maschera viene determinata nel modo seguente:  
  
1. Estrarre l'indice necessario per accedere al byte corretto nella `availableRegChunks` matrice:  
  
     `CorDebugRegister`valore >> 3  
  
2. Estrae la posizione del bit all'interno del byte indicizzato, dove bit zero è il bit meno significativo:  
  
     `CorDebugRegister`valore & 7  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
- [Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)
