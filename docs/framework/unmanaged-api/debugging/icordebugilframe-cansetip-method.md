---
title: Metodo ICorDebugILFrame::CanSetIP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.CanSetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22d0df9add0a4ce35b1a590d65e30a6756fec49c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframecansetip-method"></a>Metodo ICorDebugILFrame::CanSetIP
Ottiene un valore HRESULT che indica se è sicuro impostare il puntatore all'istruzione per la posizione di offset specificata nel codice Microsoft Intermediate Language (MSIL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `nOffset`  
 [in] L'impostazione desiderata per il puntatore all'istruzione.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `CanSetIP` metodo prima di chiamare il [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) metodo. Se `CanSetIP` restituisce qualsiasi valore HRESULT diverso da S_OK, sarà comunque possibile richiamare `ICorDebugILFrame::SetIP`, ma non c'è garanzia che il debugger continua l'esecuzione sicura e corretta del codice in fase di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug, h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
