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
ms.openlocfilehash: 2cd2238ac67713564922be440ce64a2ebc4bbf44
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396339"
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
 out Puntatore all'indirizzo di un' `ICorPublishProcess` istanza che rappresenta il processo.  
  
## <a name="remarks"></a>Commenti  
 `GetProcess`ha esito negativo se il processo non esiste o non è un processo gestito che può essere sottoposto a debug dall'utente corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorPub. idl, CorPub. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorPublish](icorpublish-interface.md)
