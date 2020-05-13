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
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210319"
---
# <a name="icordebugilframecansetip-method"></a>Metodo ICorDebugILFrame::CanSetIP
Ottiene un valore HRESULT che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato nel codice MSIL (Microsoft Intermediate Language).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nOffset`  
 in Impostazione desiderata per il puntatore all'istruzione.  
  
## <a name="remarks"></a>Osservazioni  
 Usare il `CanSetIP` metodo prima di chiamare il metodo [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) . Se `CanSetIP` restituisce un valore HRESULT diverso da S_OK, è comunque possibile richiamare `ICorDebugILFrame::SetIP` , ma non vi è alcuna garanzia che il debugger continuerà l'esecuzione sicura e corretta del codice sottoposto a debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug, h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
