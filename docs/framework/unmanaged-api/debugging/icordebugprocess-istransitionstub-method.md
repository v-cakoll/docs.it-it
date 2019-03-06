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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488188"
---
# <a name="icordebugprocessistransitionstub-method"></a>Metodo ICorDebugProcess::IsTransitionStub
Ottiene un valore che indica se un indirizzo è all'interno di uno stub che causa una transizione al codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in questione.  
  
 `pbTransitionStub`  
 [out] Un puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che causa una transizione al codice gestito; in caso contrario, *`pbTransitionStub` è `false`.  
  
## <a name="remarks"></a>Note  
 Il `IsTransitionStub` metodo utilizzabile dal codice non gestito debug passo a passo per decidere quando restituire il controllo per il gestore gestito di istruzioni.  
  
 È anche possibile stub transizione identità esaminando le informazioni contenute nel file eseguibile portabile (PE).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
