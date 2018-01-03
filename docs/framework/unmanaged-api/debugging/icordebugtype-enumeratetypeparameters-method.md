---
title: Metodo ICorDebugType::EnumerateTypeParameters
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Metodo ICorDebugType::EnumerateTypeParameters
Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che contiene il <xref:System.Type> parametri della classe indicata da ICorDebugType.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppTyParEnum`  
 [out] Un puntatore all'indirizzo di un `ICorDebugTypeEnum` che contiene i parametri del tipo.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare `EnumerateTypeParameters` se il valore di CorElementType restituito da [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) è ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE _ PTR o ELEMENT_TYPE_FNPTR. Il numero di parametri e il relativo ordine dipende dal tipo:  
  
-   ELEMENT_TYPE_CLASS o un ELEMENT_TYPE_VALUETYPE: il numero di parametri di tipo contenuto nel `ICorDebugTypeEnum` che questo metodo restituisce, variano in base al numero di parametri di tipo formale per la classe corrispondente. Ad esempio, se il tipo è `class Dict<String,int32>`, quindi `EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` che contiene oggetti che rappresentano `String` e `int32` nella sequenza.  
  
-   ELEMENT_TYPE_FNPTR: Il numero di parametri di tipo contenuto nel `ICorDebugTypeEnum` sarà uno maggiore del numero di argomenti accettati dalla funzione. Il primo parametro di tipo contenuto nel `ICorDebugTypeEnum` è il tipo restituito della funzione e i parametri di tipo successivi sono parametri della funzione.  
  
-   ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: verrà restituito un parametro di tipo. Ad esempio, se il tipo è un tipo di matrice, ad esempio `int32[]`,`EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` che contiene un oggetto che rappresenta `int32`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
