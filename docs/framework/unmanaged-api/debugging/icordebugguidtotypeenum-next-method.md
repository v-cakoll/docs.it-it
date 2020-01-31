---
title: Metodo ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 76cab0b8b5f16f24c62e31be2707c95c7e557034
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777636"
---
# <a name="icordebugguidtotypeenumnext-method"></a>Metodo ICorDebugGuidToTypeEnum::Next
Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
 in Numero di oggetti mapping da GUID a tipo da recuperare.  
  
 `values`  
 out Matrice di puntatori, ciascuno dei quali punta a un oggetto [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che esegue il mapping di un GUID Windows Runtime al relativo oggetto ICorDebugType corrispondente.  
  
 `pceltFetched`  
 out Puntatore al numero di oggetti [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) effettivamente restituiti in `values`.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
