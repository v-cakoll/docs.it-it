---
title: 'Metodo interfacce icordebugcode4:: EnumerateVariableHomes'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: ca452b230e2508f2d69c9aa38f274db506f3a906
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784093"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>Metodo interfacce icordebugcode4:: EnumerateVariableHomes
Ottiene un enumeratore per le variabili e gli argomenti locali in una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnum`  
 Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) che è un enumeratore per le variabili e gli argomenti locali in una funzione.  
  
## <a name="remarks"></a>Note  
 L'oggetto interfaccia [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) è un enumeratore standard derivato dall'interfaccia "ICorDebugEnum" che consente di enumerare gli oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) . La raccolta può includere più oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) per lo stesso indice di slot o di argomento se hanno case diverse in punti diversi della funzione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugCode4](icordebugcode4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
