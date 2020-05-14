---
title: 'Metodo IcorDebugVariableHome:: GetLiveRange'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: fb198782bb91a8301507fd6cadcffb0378230f0e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396575"
---
# <a name="icordebugvariablehomegetliverange-method"></a>Metodo IcorDebugVariableHome:: GetLiveRange
Ottiene l'intervallo nativo su cui questa variabile è attiva.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pStartOffset`  
 out Offset logico in corrispondenza del quale la variabile è la prima Live.  
  
 `pEndOffset`  
 out Offset logico immediatamente dopo il punto in cui la variabile è l'ultima volta in tempo reale.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
