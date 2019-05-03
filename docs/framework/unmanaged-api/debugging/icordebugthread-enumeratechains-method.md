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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994045"
---
# <a name="icordebugthreadenumeratechains-method"></a>Metodo ICorDebugThread::EnumerateChains
Ottiene un puntatore a interfaccia per un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in questo oggetto ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppChains`  
 [out] Un puntatore all'indirizzo di un `ICorDebugChainEnum` oggetto che consente l'enumerazione di tutti i stack concatenato in questo thread, a partire da quella attiva (ovvero, il più recente).  
  
## <a name="remarks"></a>Note  
 La catena dello stack rappresenta lo stack di chiamate fisico per il thread. Le circostanze seguenti creare un limite di catena dello stack:  
  
- Una transizione da gestito o non gestito a gestito.  
  
- Un cambio di contesto.  
  
- Un Hijack di un thread di utente del debugger.  
  
 Nel caso più semplice per un thread che esegue codice gestito esclusivamente in un singolo contesto, sarà presente una corrispondenza uno a uno tra thread e catene dello stack.  
  
 Un debugger potrebbe essere necessario modificare gli stack di chiamate fisico di tutti i thread in stack di chiamate logici. Ciò comporta l'ordinamento di catene di tutti i thread per le relative relazioni chiamante/chiamato e il relativo raggruppamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
