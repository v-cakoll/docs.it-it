---
title: Metodo ICorDebugHeapValue2::CreateHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue2.CreateHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eeef3215c3740cdaa7d1b78b73fde9e76d7b40c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue2createhandle-method"></a>Metodo ICorDebugHeapValue2::CreateHandle
Crea un handle del tipo specificato per il valore di heap rappresentato dall'oggetto ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `type`  
 [in] Valore dell'enumerazione CorDebugHandleType che specifica il tipo di handle da creare.  
  
 `ppHandle`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugHandleValue che rappresenta il nuovo handle per il valore dell'heap.  
  
## <a name="remarks"></a>Note  
 L'handle verrà creato nel dominio dell'applicazione che è associato il valore dell'heap e non sarà più valido se il dominio applicazione viene scaricato.  
  
 Più chiamate a questa funzione per lo stesso valore di heap creerà più handle. Poiché gli handle di influire sulle prestazioni del garbage collector, il debugger deve limitarsi a un numero relativamente ridotto di handle (circa 256) che sono attive contemporaneamente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
