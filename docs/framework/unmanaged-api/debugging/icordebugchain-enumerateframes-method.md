---
title: Metodo ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d408f317b546fb7e8314e904e6f5ad9e6296ae6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403266"
---
# <a name="icordebugchainenumerateframes-method"></a>Metodo ICorDebugChain::EnumerateFrames
Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppFrames`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugFrameEnum che è l'enumeratore per gli stack frame.  
  
## <a name="remarks"></a>Note  
 La catena rappresenta lo stack di chiamate fisico per il thread.  
  
 Il `EnumerateFrames` metodo deve essere chiamato solo per le catene gestite. L'API di debug non fornisce metodi per ottenere i frame contenuti nelle catene non gestite. Il debugger deve utilizzare altri mezzi per ottenere queste informazioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
