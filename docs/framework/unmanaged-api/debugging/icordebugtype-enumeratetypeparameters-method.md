---
title: Metodo ICorDebugType::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16cf17d43fcad3c4f7a710678bbdc056f840eaca
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736802"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Metodo ICorDebugType::EnumerateTypeParameters
Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che contiene il <xref:System.Type> parametri della classe a cui fa riferimento questa ICorDebugType.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppTyParEnum`  
 [out] Un puntatore all'indirizzo di un `ICorDebugTypeEnum` che contiene i parametri del tipo.  
  
## <a name="remarks"></a>Note  
 È possibile usare `EnumerateTypeParameters` se il valore CorElementType restituito da [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) è ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE _ PTR o ELEMENT_TYPE_FNPTR. Il numero di parametri e il loro ordine dipende dal tipo:  
  
- ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: Il numero di parametri di tipo contenuto nel `ICorDebugTypeEnum` che termina, questo metodo varia in base al numero di parametri di tipo formale per la classe corrispondente. Ad esempio, se il tipo è `class Dict<String,int32>`, quindi `EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` che contiene gli oggetti che rappresentano `String` e `int32` nella sequenza.  
  
- ELEMENT_TYPE_FNPTR: Il numero di parametri di tipo contenuto nel `ICorDebugTypeEnum` sarà uno maggiore del numero di argomenti accettati dalla funzione. Il primo parametro di tipo contenuto nel `ICorDebugTypeEnum` è il tipo restituito della funzione e i parametri di tipo successive sono parametri della funzione.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: Verrà restituito un parametro di tipo. Ad esempio, se il tipo è un tipo di matrice, ad esempio `int32[]`,`EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` che contiene un oggetto che rappresenta `int32`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
