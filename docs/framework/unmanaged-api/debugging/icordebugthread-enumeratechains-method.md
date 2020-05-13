---
title: Metodo ICorDebugThread::EnumerateChains
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 711fccd65379bc3e5e178869e7220dd84fd07fbe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379707"
---
# <a name="icordebugthreadenumeratechains-method"></a>Metodo ICorDebugThread::EnumerateChains
Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in questo oggetto ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppChains`  
 out Puntatore all'indirizzo di un `ICorDebugChainEnum` oggetto che consente l'enumerazione di tutte le catene dello stack nel thread, a partire dalla catena attiva (ovvero la più recente).  
  
## <a name="remarks"></a>Osservazioni  
 La catena di stack rappresenta lo stack di chiamate fisico per il thread. Nelle circostanze seguenti viene creato un limite della catena dello stack:  
  
- Una transizione da gestita a non gestita o non gestita.  
  
- Cambio di contesto.  
  
- Hijack del debugger di un thread utente.  
  
 Nel caso semplice per un thread che esegue codice puramente gestito in un unico contesto, esiste una corrispondenza uno-a-uno tra i thread e le catene dello stack.  
  
 Un debugger potrebbe voler ridisporre gli stack di chiamate fisici di tutti i thread in stack di chiamate logiche. Questo comporterebbe l'ordinamento di tutte le catene dei thread in base alle relazioni chiamante/chiamato e al loro raggruppamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
