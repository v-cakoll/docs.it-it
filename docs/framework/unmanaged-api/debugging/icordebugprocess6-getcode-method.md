---
title: Metodo ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 178d1df7e6c8246b18afed442e944c49051b6597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209266"
---
# <a name="icordebugprocess6getcode-method"></a>Metodo ICorDebugProcess6::GetCode
Ottiene informazioni sul codice gestito in un indirizzo di codice specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a>Parametri  
 `codeAddress`  
 in Valore [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) che specifica l'indirizzo iniziale del segmento di codice gestito.  
  
 `ppCode`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta un segmento di codice gestito.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
