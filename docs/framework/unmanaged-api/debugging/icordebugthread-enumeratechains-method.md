---
title: Metodo ICorDebugThread::EnumerateChains
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.EnumerateChains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67b5a5da0a0053536ab4331e9d134464a4330500
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadenumeratechains-method"></a>Metodo ICorDebugThread::EnumerateChains
Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum contenente tutte le catene dello stack di questo oggetto ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppChains`  
 [out] Un puntatore all'indirizzo di un `ICorDebugChainEnum` oggetto che consente l'enumerazione dello stack di concatenato in questo thread, a partire da quella attiva (ovvero, la più recente).  
  
## <a name="remarks"></a>Note  
 La catena dello stack rappresenta lo stack di chiamate fisico per il thread. Le seguenti circostanze creare un limite di catena dello stack:  
  
-   Una transizione da gestito o non gestito a gestito.  
  
-   Un cambio di contesto.  
  
-   Un Hijack di un thread di utente del debugger.  
  
 Nel caso più semplice per un thread che esegue codice gestito esclusivamente in un contesto singolo, sarà presente una corrispondenza tra thread e catene dello stack.  
  
 Un debugger potrebbe essere necessario modificare gli stack di chiamate fisico di tutti i thread in stack di chiamata logico. Ciò comporta l'ordinamento di catene di tutti i thread per le relative relazioni chiamante/chiamato e il relativo raggruppamento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
