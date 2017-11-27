---
title: Metodo ICorDebugThread::GetHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3cd5f7191c00b7c6b07bacc463d906982c994578
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgethandle-method"></a>Metodo ICorDebugThread::GetHandle
Ottiene l'handle corrente per la parte attiva del ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `phThreadHandle`  
 [out] Un puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.  
  
## <a name="remarks"></a>Note  
 L'handle può cambiare durante il processo viene eseguito e può essere diverso per le diverse parti del thread.  
  
 Questo handle è di proprietà dell'API di debug. Il debugger deve duplicarlo prima di utilizzarlo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
