---
title: Metodo ICorDebugEval2::CreateValueForType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CreateValueForType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cc2760b1c303141372aed824bda71ebdae8ffe0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>Parametri  
 `pType`  
 [in] Puntatore a un oggetto ICorDebugType che rappresenta il tipo.  
  
 `ppValue`  
 [out] Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta il valore.  
  
## <a name="remarks"></a>Note  
 `CreateValueForType`Consente di generalizzare [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) , consentendo di specificare un tipo di oggetto arbitrario, inclusi i tipi costruiti, ad esempio `List<int>`. L'unico scopo di questo metodo consiste nel generare un valore che può essere passato a una valutazione della funzione.  
  
 Il tipo deve essere una classe o un tipo di valore. È possibile utilizzare questo metodo per creare valori di matrice o stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
