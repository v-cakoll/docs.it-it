---
title: Metodo ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: 21890f8130ec677cb88f2f5d7ef648aa19e67e71
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213062"
---
# <a name="icordebugnativeframecansetip-method"></a>Metodo ICorDebugNativeFrame::CanSetIP
Ottiene un HRESULT che indica se è sicuro impostare il puntatore all'istruzione (IP) sulla posizione di offset specificata nel codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nOffset`  
 in Impostazione desiderata per il puntatore all'istruzione.  
  
## <a name="remarks"></a>Osservazioni  
 Usare il `CanSetIP` metodo prima di chiamare il metodo [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) . Se `CanSetIP` restituisce un valore HRESULT diverso da S_OK, è comunque possibile richiamare `ICorDebugNativeFrame::SetIP` , ma non vi è alcuna garanzia che il debugger continuerà l'esecuzione sicura e corretta del codice sottoposto a debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
