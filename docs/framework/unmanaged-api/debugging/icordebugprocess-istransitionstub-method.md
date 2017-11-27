---
title: Metodo ICorDebugProcess::IsTransitionStub
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsTransitionStub
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60f6e4116768d2d855edd941df796167754b3ab4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessistransitionstub-method"></a>Metodo ICorDebugProcess::IsTransitionStub
Ottiene un valore che indica se un indirizzo è all'interno di uno stub che causerà una transizione da codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo in questione.  
  
 `pbTransitionStub`  
 [out] Un puntatore a un valore booleano che è `true` se l'indirizzo specificato si trova all'interno di uno stub che causerà una transizione a codice gestito; in caso contrario *`pbTransitionStub` è `false`.  
  
## <a name="remarks"></a>Note  
 Il `IsTransitionStub` metodo può essere usato da passo a passo il codice non gestito per decidere quando restituire il controllo per il gestore di istruzioni gestito.  
  
 È possibile anche gli stub di transizione identità esaminando le informazioni contenute nel file eseguibile portabile (PE).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
