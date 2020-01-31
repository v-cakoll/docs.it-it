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
ms.openlocfilehash: b2c381d093069f5ee86be1b19d75f5c2d69ad9fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791303"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Metodo ICorDebugType::EnumerateTypeParameters
Ottiene un puntatore a interfaccia a un ICorDebugTypeEnum che contiene i parametri di <xref:System.Type> della classe a cui fa riferimento ICorDebugType.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppTyParEnum`  
 out Puntatore all'indirizzo di un `ICorDebugTypeEnum` che contiene i parametri del tipo.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare `EnumerateTypeParameters` se il valore CorElementType restituito da [ICorDebugType:: GetType](icordebugtype-gettype-method.md) è ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR o ELEMENT_TYPE_FNPTR. Il numero di parametri e il relativo ordine dipendono dal tipo:  
  
- ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: il numero di parametri di tipo contenuti nel `ICorDebugTypeEnum` restituito da questo metodo dipende dal numero di parametri di tipo formale per la classe corrispondente. Se, ad esempio, il tipo è `class Dict<String,int32>`, `EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` contenente oggetti che rappresentano `String` e `int32` in sequenza.  
  
- ELEMENT_TYPE_FNPTR: il numero di parametri di tipo contenuti nel `ICorDebugTypeEnum` sarà maggiore di uno rispetto al numero di argomenti accettati dalla funzione. Il primo parametro di tipo contenuto nell'`ICorDebugTypeEnum` è il tipo restituito per la funzione e i parametri di tipo successivi sono i parametri della funzione.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: verrà restituito un parametro di tipo. Se, ad esempio, il tipo è un tipo di matrice, ad esempio `int32[]`,`EnumerateTypeParameters` restituirà un `ICorDebugTypeEnum` contenente un oggetto che rappresenta `int32`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
