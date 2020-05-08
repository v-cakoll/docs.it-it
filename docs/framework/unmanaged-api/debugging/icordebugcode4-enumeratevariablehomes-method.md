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
ms.openlocfilehash: 5f731b1459542c3f5378790b21f2ea576e89ad97
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893347"
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
  
## <a name="remarks"></a>Osservazioni  
 L'oggetto interfaccia [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) è un enumeratore standard derivato dall'interfaccia "ICorDebugEnum" che consente di enumerare gli oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) . La raccolta può includere più oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) per lo stesso indice di slot o di argomento se hanno case diverse in punti diversi della funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugCode4](icordebugcode4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
