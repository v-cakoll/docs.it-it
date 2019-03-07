---
title: Metodo ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43532888d181adcb7a7e3760f2a5e3d8f664a35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492283"
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
  
## <a name="parameters"></a>Parametri  
 `pStart`  
 [out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo iniziale del frame dello stack rappresentato da questo `ICorDebugFrame` oggetto.  
  
 `pEnd`  
 [out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo finale del frame dello stack rappresentato da questo `ICorDebugFrame` oggetto.  
  
## <a name="remarks"></a>Note  
 L'intervallo di indirizzi dello stack è utile per riunire tracce dello stack con interfoliazione raccolte da più motori di debug. L'intervallo numerico non fornisce informazioni sul contenuto del frame dello stack. È significativo solo per il confronto dei percorsi dello stack frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
