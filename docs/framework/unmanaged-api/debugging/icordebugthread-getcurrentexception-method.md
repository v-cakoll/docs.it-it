---
title: Metodo ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: 3a4da6f958407c0b704ffb7372a77b7f022fc824
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379761"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Metodo ICorDebugThread::GetCurrentException
Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione attualmente generata dal codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppExceptionObject`  
 out Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata attualmente dal codice gestito.  
  
## <a name="remarks"></a>Osservazioni  
 L'oggetto Exception sarà presente dal momento in cui viene generata l'eccezione fino alla fine del `catch` blocco. Una valutazione della funzione, eseguita dai metodi ICorDebugEval, eliminerà l'oggetto eccezione durante l'installazione e lo ripristinerà al completamento.  
  
 È possibile nidificare le eccezioni, ad esempio se un'eccezione viene generata in un filtro o in una valutazione di funzione, quindi potrebbero esserci più eccezioni in attesa in un singolo thread. `GetCurrentException`Restituisce l'eccezione più recente.  
  
 L'oggetto eccezione e il tipo possono cambiare per tutta la durata dell'eccezione. Ad esempio, dopo che è stata generata un'eccezione di tipo x, il Common Language Runtime (CLR) potrebbe esaurire la memoria e innalzarlo di livello a un'eccezione di memoria insufficiente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
