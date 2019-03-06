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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b27e40618d6128c21e99745ca45e139a9c21c843
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475034"
---
# <a name="icordebugeval2createvaluefortype-method"></a>Metodo ICorDebugEval2::CreateValueForType
Ottiene un puntatore a un nuovo oggetto ICorDebugValue del tipo specificato, con un valore iniziale pari a zero o null.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pType`  
 [in] Puntatore a un oggetto ICorDebugType che rappresenta il tipo.  
  
 `ppValue`  
 [out] Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta il valore.  
  
## <a name="remarks"></a>Note  
 `CreateValueForType` Consente di generalizzare [ICorDebugEval](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) da cui è possibile specificare un tipo di oggetto arbitrario, inclusi i tipi costruiti, ad esempio `List<int>`. L'unico scopo di questo metodo deve generare un valore che può essere passato a una valutazione della funzione.  
  
 Il tipo deve essere una classe o un tipo di valore. È non è possibile usare questo metodo per creare i valori della matrice o i valori stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
