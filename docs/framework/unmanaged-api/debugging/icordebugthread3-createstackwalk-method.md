---
title: Metodo ICorDebugThread3::CreateStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: 64f6bc9abb8105cdfa942c2aaca71994e8a91765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791407"
---
# <a name="icordebugthread3createstackwalk-method"></a>Metodo ICorDebugThread3::CreateStackWalk
Crea un oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) per il thread il cui stack si vuole rimuovere.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppStackWalk`  
 out Puntatore all'indirizzo dell'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) per il thread di cui si desidera rimuovere lo stack.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Creazione dell'oggetto `ICorDebugStackWalk` completata.|  
|E_FAIL|L'oggetto `ICorDebugStackWalk` non è stato creato.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Se il metodo `CreateStackWalk` ha esito positivo, il contesto dell'oggetto `ICorDebugStackWalk` restituito viene impostato sul contesto corrente del thread.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
