---
title: Metodo ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: d924de33c8ec49501be0ee7700b2eee8c79bb950
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397120"
---
# <a name="icordebugvariablesymbolgetsize-method"></a>Metodo ICorDebugVariableSymbol::GetSize
Ottiene le dimensioni di una variabile in byte.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pcbValue`  
 Puntatore a un intero senza segno a 32 bit che contiene le dimensioni della variabile.  
  
## <a name="remarks"></a>Commenti  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
