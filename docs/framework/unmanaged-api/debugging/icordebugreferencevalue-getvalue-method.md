---
title: Metodo ICorDebugReferenceValue::GetValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.GetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bb11810c14f383b74c565b3bd30602c22b026e62
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluegetvalue-method"></a>Metodo ICorDebugReferenceValue::GetValue
Ottiene l'indirizzo di memoria corrente dell'oggetto di riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pValue`  
 [out] Un puntatore a un `CORDB_ADDRESS` valore che specifica l'indirizzo dell'oggetto a cui fa riferimento questo oggetto ICorDebugReferenceValue.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
