---
title: Interfaccia ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: 0e480db953131d7771e493a8f367154a7d17dada
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396634"
---
# <a name="icordebugtype2-interface"></a>Interfaccia ICorDebugType2
Estende l'interfaccia ICorDebugType per recuperare l'identificatore di tipo di un tipo di base o di un tipo complesso (definito dall'utente).  
  
## <a name="methods"></a>Metodi  
  
|Metodo||  
|------------|-|  
|[Metodo GetTypeID](icordebugtype2-gettypeid-method.md)|Ottiene un [COR_TYPEID](cor-typeid-structure.md) per questo tipo.|  
  
## <a name="remarks"></a>Commenti  
 Questa interfaccia è un'estensione logica dell'interfaccia ICorDebugType.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="example"></a>Esempio  
 Il frammento di codice seguente illustra l'uso del metodo [Metodo icordebugtype2:: GetTypeID](icordebugtype2-gettypeid-method.md) .  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
