---
title: Metodo ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 366b5124cc66a4e9a1c3bd4e77f604f15ba8d8a8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379677"
---
# <a name="icordebugthread4getblockingobjects-method"></a>Metodo ICorDebugThread4::GetBlockingObjects
Fornisce un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) che forniscono informazioni di blocco del thread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Parametri  
 `ppBlockingObjectEnum`  
 out Puntatore a un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
## <a name="remarks"></a>Osservazioni  
 Il primo elemento nell'enumerazione restituita corrisponde alla prima struttura che blocca il thread. Il secondo elemento corrisponde a un elemento di blocco rilevato durante l'esecuzione di una chiamata di procedura asincrona (APC) quando viene bloccato sul primo e così via.  
  
 L'enumerazione è valida solo per la durata dello stato sincronizzato corrente.  
  
 Questo metodo deve essere chiamato quando l'oggetto del debug è in stato SYNCHRONIZED.  
  
 Se `ppBlockingObjectEnum` non è un puntatore valido, il risultato è indefinito.  
  
 Se un thread è bloccato e non è possibile determinare l'errore, il metodo restituisce un valore HRESULT che indica un errore. in caso contrario, restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugThread4](icordebugthread4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
