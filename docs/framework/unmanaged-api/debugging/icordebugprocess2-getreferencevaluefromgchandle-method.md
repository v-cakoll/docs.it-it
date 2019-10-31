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
ms.openlocfilehash: 47647bf0460507b4c88b47bf87bfcc3bf620aecc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137213"
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
 in Puntatore a un oggetto gestito che dispone di un handle Garbage Collection. Questo valore è un oggetto <xref:System.IntPtr> e può essere recuperato dall'<xref:System.Runtime.InteropServices.GCHandle> per l'oggetto gestito.  
  
 `pOutValue`  
 out Puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.  
  
## <a name="remarks"></a>Note  
 Non confondere il valore di riferimento restituito con un Garbage Collection valore di riferimento.  
  
 Il riferimento restituito si comporta come un riferimento normale. Viene disabilitato quando l'esecuzione del codice continua dopo un punto di interruzione. La durata dell'oggetto di destinazione non è influenzata dalla durata del valore di riferimento.  
  
> [!NOTE]
> Il metodo `GetReferenceValueFromGCHandle` non convalida l'handle. Pertanto, il metodo `GetReferenceValueFromGCHandle` può potenzialmente danneggiare sia il debugger che il codice sottoposto a debug se viene passato un handle non valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
