---
title: Metodo ICorDebugThread2::GetConnectionID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c0e76b179854a380e66ac9daedffa8ccf4aa4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthread2getconnectionid-method"></a>Metodo ICorDebugThread2::GetConnectionID
Ottiene l'identificatore di connessione per l'oggetto ICorDebugThread2.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwConnectionId`  
 [out] Oggetto `CONNID` che rappresenta l'identificatore di connessione.  
  
## <a name="remarks"></a>Note  
 Il `GetConnectionID` restituisce zero nel `pdwConnectionId` parametro, se il thread non è parte di una connessione.  
  
 Se il thread è connesso a un'istanza di Microsoft SQL Server 2005 Analysis Services (SSAS), il `CONNID` esegue il mapping a un identificatore di processo server (SPID).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
