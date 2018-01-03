---
title: Metodo ICorDebugFrame::GetStackRange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c4c9c0a531d93ca2c7c72f50bcd2f7ee98887e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetstackrange-method"></a>Metodo ICorDebugFrame::GetStackRange
Ottiene l'intervallo di indirizzi assoluti dello stack frame corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pStart`  
 [out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo iniziale dello stack frame rappresentato da questo `ICorDebugFrame` oggetto.  
  
 `pEnd`  
 [out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo finale dello stack frame rappresentato da questo `ICorDebugFrame` oggetto.  
  
## <a name="remarks"></a>Note  
 L'intervallo di indirizzi dello stack è utile per riunire le tracce dello stack con interfoliazione raccolte da più motori di debug. L'intervallo numerico non fornisce informazioni sul contenuto del frame dello stack. È significativo solo per il confronto di percorsi dello stack frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
