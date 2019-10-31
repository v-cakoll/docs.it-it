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
ms.openlocfilehash: 828e4dc67cb93d0a35879e94b54c9fac6e5bda16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124079"
---
# <a name="icordebugframegetstackrange-method"></a>Metodo ICorDebugFrame::GetStackRange
Ottiene l'intervallo di indirizzi assoluto di questo stack frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStart`  
 out Puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo iniziale della stack frame rappresentata da questo oggetto `ICorDebugFrame`.  
  
 `pEnd`  
 out Puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo finale della stack frame rappresentata da questo oggetto `ICorDebugFrame`.  
  
## <a name="remarks"></a>Note  
 L'intervallo di indirizzi dello stack è utile per riunire tracce dello stack Interleaved raccolte da più motori di debug. L'intervallo numerico non fornisce informazioni sul contenuto del stack frame. È significativo solo per il confronto dei percorsi di stack frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
