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
ms.openlocfilehash: 770a9280d27c84b950e00e71328c9b28e61c9e7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084813"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a>Metodo ICorDebugEval2::NewParameterizedObjectNoConstructor
Crea un'istanza di un nuovo oggetto di tipo con parametri della classe specificata senza provare a chiamare un metodo del costruttore.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pClass`  
 in Puntatore a un oggetto ICorDebugClass che rappresenta la classe dell'oggetto di cui creare un'istanza.  
  
 `nTypeArgs`  
 in Numero di argomenti di tipo passati.  
  
 `ppTypeArgs`  
 in Matrice di puntatori, ciascuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo per l'oggetto di cui viene creata un'istanza.  
  
## <a name="remarks"></a>Note  
 Il metodo `NewParameterizedObjectNoConstructor` avrà esito negativo se viene passato un numero errato di argomenti di tipo o tipi non corretti di argomenti di tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
