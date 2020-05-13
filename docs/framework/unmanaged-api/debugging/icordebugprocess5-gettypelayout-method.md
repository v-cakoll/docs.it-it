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
ms.openlocfilehash: 861af4ba9c6f4d4bdb16abb9d4e1fd79debac59b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205569"
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
  
## <a name="remarks"></a>Osservazioni  
 Il `ICorDebugProcess5::GetTypeLayout` metodo fornisce informazioni su un oggetto in base alla relativa [COR_TYPEID](cor-typeid-structure.md), che viene restituita da diversi altri metodi [ICorDebugProcess5](icordebugprocess5-interface.md) . Le informazioni vengono fornite da una struttura [COR_TYPE_LAYOUT](cor-type-layout-structure.md) popolata dal metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Struttura COR_TYPE_LAYOUT](cor-type-layout-structure.md)
- [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
