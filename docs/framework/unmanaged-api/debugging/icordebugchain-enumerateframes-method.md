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
ms.openlocfilehash: 0b024d3396dfe1796fcb18afa122d4aee39c4ccc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132715"
---
# <a name="icordebugchainenumerateframes-method"></a>Metodo ICorDebugChain::EnumerateFrames
Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppFrames`  
 out Puntatore all'indirizzo di un oggetto ICorDebugFrameEnum che rappresenta l'enumeratore per gli stack frame.  
  
## <a name="remarks"></a>Note  
 La catena rappresenta lo stack di chiamate fisico per il thread.  
  
 Il metodo di `EnumerateFrames` deve essere chiamato solo per le catene gestite. L'API di debug non fornisce metodi per ottenere i frame contenuti nelle catene non gestite. Per ottenere queste informazioni, il debugger deve utilizzare altri mezzi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
