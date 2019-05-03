---
title: Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6feef7b1e1f09107cd2a57555df07bebec86effa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667028"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a>Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor
Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza effettuare alcun tentativo di chiamare un metodo del costruttore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pClass`  
 [in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe dell'oggetto da cui creare istanze.  
  
 `nTypeArgs`  
 [in] Il numero di argomenti tipo passati.  
  
 `ppTypeArgs`  
 [in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto che viene viene creata un'istanza.  
  
## <a name="remarks"></a>Note  
 Il `NewParameterizedObjectNoConstructor` metodo avrà esito negativo se un numero errato di argomenti di tipo o i tipi errati di argomenti tipo passati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
