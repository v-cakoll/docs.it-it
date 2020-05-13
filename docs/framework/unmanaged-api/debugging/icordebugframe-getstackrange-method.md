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
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205154"
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
 out Puntatore a un oggetto `CORDB_ADDRESS` che specifica l'indirizzo iniziale del stack frame rappresentato da questo `ICorDebugFrame` oggetto.  
  
 `pEnd`  
 out Puntatore a un `CORDB_ADDRESS` oggetto che specifica l'indirizzo finale della stack frame rappresentata da questo `ICorDebugFrame` oggetto.  
  
## <a name="remarks"></a>Osservazioni  
 L'intervallo di indirizzi dello stack è utile per riunire tracce dello stack Interleaved raccolte da più motori di debug. L'intervallo numerico non fornisce informazioni sul contenuto del stack frame. È significativo solo per il confronto dei percorsi di stack frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
