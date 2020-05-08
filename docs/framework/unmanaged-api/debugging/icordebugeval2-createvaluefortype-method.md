---
title: Metodo ICorDebugEval2::CreateValueForType
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: fd7acaa8bcb4d53893855bcd25ff68cf26e30354
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976161"
---
# <a name="icordebugeval2createvaluefortype-method"></a>Metodo ICorDebugEval2::CreateValueForType
Ottiene un puntatore a un nuovo ICorDebugValue del tipo specificato, con un valore iniziale pari a zero o null.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pType`  
 in Puntatore a un oggetto ICorDebugType che rappresenta il tipo.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta il valore.  
  
## <a name="remarks"></a>Osservazioni  
 `CreateValueForType`generalizza [ICorDebugEval:: CreateValue](icordebugeval-createvalue-method.md) consentendo di specificare un tipo di oggetto arbitrario, inclusi i tipi costruiti, ad `List<int>`esempio. L'unico scopo di questo metodo è generare un valore che può essere passato a una valutazione di funzione.  
  
 Il tipo deve essere una classe o un tipo valore. Non è possibile usare questo metodo per creare valori di stringa o di matrice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
