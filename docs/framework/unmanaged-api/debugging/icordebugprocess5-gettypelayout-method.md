---
title: Metodo ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 306d881c05c2fcdb15a53a439bfce6eff3afffa8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792305"
---
# <a name="icordebugprocess5gettypelayout-method"></a>Metodo ICorDebugProcess5::GetTypeLayout
Ottiene informazioni sul layout di un oggetto in memoria in base al relativo identificatore di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parametri  
 `id`  
 in Token [COR_TYPEID](cor-typeid-structure.md) che specifica il tipo di cui si desidera il layout.  
  
 `pLayout`  
 out Puntatore a una struttura [COR_TYPE_LAYOUT](cor-type-layout-structure.md) che contiene informazioni sul layout dell'oggetto in memoria.  
  
## <a name="remarks"></a>Note  
 Il metodo `ICorDebugProcess5::GetTypeLayout` fornisce informazioni su un oggetto in base al relativo [COR_TYPEID](cor-typeid-structure.md), restituito da diversi altri metodi [ICorDebugProcess5](icordebugprocess5-interface.md) . Le informazioni vengono fornite da una struttura [COR_TYPE_LAYOUT](cor-type-layout-structure.md) popolata dal metodo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Struttura COR_TYPE_LAYOUT](cor-type-layout-structure.md)
- [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
