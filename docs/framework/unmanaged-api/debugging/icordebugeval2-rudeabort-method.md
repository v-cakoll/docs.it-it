---
title: Metodo ICorDebugEval2::RudeAbort
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: a486935d5d53a6fc7d862160ed1186c5774814c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084791"
---
# <a name="icordebugeval2rudeabort-method"></a>Metodo ICorDebugEval2::RudeAbort
Interrompe il calcolo che questo `ICorDebugEval2` sta attualmente eseguendo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Note  
 `RudeAbort` non rilascia alcun blocco che l'analizzatore possiede, quindi lascia la sessione di debug in uno stato non sicuro. Chiamare questo metodo con estrema cautela.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
