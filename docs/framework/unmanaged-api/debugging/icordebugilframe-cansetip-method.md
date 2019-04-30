---
title: Metodo ICorDebugILFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49cef22e88613fe4c4dfb3fb35a92977977b1827
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988637"
---
# <a name="icordebugilframecansetip-method"></a>Metodo ICorDebugILFrame::CanSetIP
Ottiene un valore HRESULT che indica se è sicuro impostare il puntatore all'istruzione per la posizione di offset specificata nel codice Microsoft Intermediate Language (MSIL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nOffset`  
 [in] L'impostazione desiderata per il puntatore all'istruzione.  
  
## <a name="remarks"></a>Note  
 Usare la `CanSetIP` metodo prima di chiamare il [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) (metodo). Se `CanSetIP` restituisce qualsiasi valore HRESULT diverso da S_OK, sarà comunque possibile richiamare `ICorDebugILFrame::SetIP`, ma non c'è garanzia che il debugger continua l'esecuzione sicura e corretta del codice sottoposto a debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug,h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
