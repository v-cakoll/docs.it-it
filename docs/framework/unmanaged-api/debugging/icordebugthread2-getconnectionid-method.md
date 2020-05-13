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
ms.openlocfilehash: c630daa50d465622c421381ac080eaa8d9d8d01d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379068"
---
# <a name="icordebugthread2getconnectionid-method"></a>Metodo ICorDebugThread2::GetConnectionID
Ottiene l'identificatore di connessione per questo oggetto ICorDebugThread2.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwConnectionId`  
 out Oggetto `CONNID` che rappresenta l'identificatore di connessione.  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetConnectionID` metodo restituisce zero nel `pdwConnectionId` parametro, se il thread non fa parte di una connessione.  
  
 Se il thread è connesso a un'istanza di Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` esegue il mapping a un identificatore di processo del server (SPID).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
