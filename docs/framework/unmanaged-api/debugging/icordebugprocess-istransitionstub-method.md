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
ms.openlocfilehash: ab2121605f974fdf3f9053214a4d29d8b0dd72db
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83211046"
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
 in `CORDB_ADDRESS`Valore che specifica l'indirizzo in questione.  
  
 `pbTransitionStub`  
 out Puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che provocherà una transizione al codice gestito; in caso contrario, * `pbTransitionStub` è `false` .  
  
## <a name="remarks"></a>Osservazioni  
 Il `IsTransitionStub` metodo può essere usato dal codice dell'istruzione non gestita per decidere quando restituire il controllo di avanzamento al gestore di debug gestito.  
  
 È anche possibile identificare gli stub di transizione esaminando le informazioni nel file eseguibile di tipo PE.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
