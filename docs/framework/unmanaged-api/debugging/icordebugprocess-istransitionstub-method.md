---
title: Metodo ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139382"
---
# <a name="icordebugprocessistransitionstub-method"></a>Metodo ICorDebugProcess::IsTransitionStub
Ottiene un valore che indica se un indirizzo si trova all'interno di uno stub che provocherà una transizione al codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in Valore `CORDB_ADDRESS` che specifica l'indirizzo in questione.  
  
 `pbTransitionStub`  
 out Puntatore a un valore booleano che viene `true` se l'indirizzo specificato si trova all'interno di uno stub che provocherà una transizione al codice gestito; in caso contrario, *`pbTransitionStub` è `false`.  
  
## <a name="remarks"></a>Note  
 Il metodo `IsTransitionStub` può essere usato dal codice dell'istruzione non gestita per decidere quando restituire il controllo di avanzamento al gestore di debug gestito.  
  
 È anche possibile identificare gli stub di transizione esaminando le informazioni nel file eseguibile di tipo PE.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
