---
title: Funzione CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 1d190c5b558c7c523be09267e59eab7c5611563a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793862"
---
# <a name="createcordbobject-function"></a>Funzione CreateCordbObject
Crea un'interfaccia del debugger ([ICorDebug](icordebug-interface.md)) che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iDebuggerVersion`  
 [in] Versione del debugger del processo di destinazione. Questo parametro deve essere CorDebugVersion_2_0 per il debug remoto.  
  
 `ppCordb`  
 out Puntatore a un puntatore a un oggetto di cui verrà eseguito il cast a un'interfaccia [ICorDebug](icordebug-interface.md) e restituito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.  
  
 E_INVALIDARG  
 `ppCordb` è null o `iDebuggerVersion` non è CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Non è possibile allocare memoria sufficiente per `ppCordb`.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Altri errori.  
  
## <a name="remarks"></a>Note  
 L'interfaccia [ICorDebug](icordebug-interface.md) restituita in `ppCordb` è l'interfaccia di debug di primo livello per tutti i servizi di debug gestito.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Libreria:** mscordbi_macx86. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
