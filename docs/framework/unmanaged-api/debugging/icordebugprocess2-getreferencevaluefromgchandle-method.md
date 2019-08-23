---
title: Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21da325ee58df65ac449464f8292f2ba94d99338
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943289"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
Ottiene un puntatore di riferimento all'oggetto gestito specificato con un handle Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `handle`  
 in Puntatore a un oggetto gestito che dispone di un handle Garbage Collection. Questo valore è un <xref:System.IntPtr> oggetto e può essere recuperato <xref:System.Runtime.InteropServices.GCHandle> da per l'oggetto gestito.  
  
 `pOutValue`  
 out Puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.  
  
## <a name="remarks"></a>Note  
 Non confondere il valore di riferimento restituito con un Garbage Collection valore di riferimento.  
  
 Il riferimento restituito si comporta come un riferimento normale. Viene disabilitato quando l'esecuzione del codice continua dopo un punto di interruzione. La durata dell'oggetto di destinazione non è influenzata dalla durata del valore di riferimento.  
  
> [!NOTE]
> Il `GetReferenceValueFromGCHandle` metodo non convalida l'handle. Pertanto, il `GetReferenceValueFromGCHandle` metodo può potenzialmente danneggiare sia il debugger che il codice sottoposto a debug se viene passato un handle non valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
