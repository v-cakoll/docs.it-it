---
title: Metodo ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: 0368349e6c6a566cb569738bf3bda40eb9f5de96
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790742"
---
# <a name="icorpublishgetprocess-method"></a>Metodo ICorPublish::GetProcess
Ottiene un'istanza di [ICorPublishProcess](icorpublishprocess-interface.md) che rappresenta il processo con l'identificatore specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pid`  
 in Identificatore del processo.  
  
 `ppProcess`  
 out Puntatore all'indirizzo di un'istanza `ICorPublishProcess` che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 `GetProcess` ha esito negativo se il processo non esiste o non è un processo gestito che può essere sottoposto a debug dall'utente corrente.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorPublish](icorpublish-interface.md)
