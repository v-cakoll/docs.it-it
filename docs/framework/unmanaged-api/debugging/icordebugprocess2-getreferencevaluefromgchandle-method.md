---
title: Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ac4cc32be6914ea858d32b8699a695588f0a1e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire un'operazione di garbage collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `handle`  
 [in] Puntatore a un oggetto gestito che presenta un handle di garbage collection. Questo valore è un <xref:System.IntPtr> dell'oggetto e può essere recuperato dal <xref:System.Runtime.InteropServices.GCHandle> per l'oggetto gestito.  
  
 `pOutValue`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.  
  
## <a name="remarks"></a>Note  
 Non confondere il valore restituito di riferimento con un valore di riferimento di garbage collection.  
  
 Il riferimento restituito si comporta come un normale riferimento. Viene disabilitato quando l'esecuzione del codice continua dopo un punto di interruzione. La durata dell'oggetto di destinazione non è interessata dalla durata del valore di riferimento.  
  
> [!NOTE]
>  Il `GetReferenceValueFromGCHandle` metodo non convalida l'handle. Pertanto, il `GetReferenceValueFromGCHandle` metodo può potenzialmente danneggiare il debugger sia il codice sottoposto a debug se viene passato un handle non valido.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
