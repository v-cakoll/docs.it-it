---
title: Enumerazione CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: cc839e9b2a28dc428ae7cc87c9d080c4b7612a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098887"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>Enumerazione CorDebugCodeInvokeKind
Descrive in che modo una funzione esportata richiama il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Se il codice gestito viene richiamato con questo metodo, in un secondo momento dovrà essere individuato mediante eventi espliciti o punti di interruzione.<br /><br /> --oppure--<br /><br /> È possibile che alcune parti di codice gestito chiamate dal metodo vadano perdute perché non esiste un modo semplice per arrestarlo.<br /><br /> --oppure--<br /><br /> Il metodo può non richiamare il codice gestito.|  
|`CODE_INVOKE_KIND_RETURN`|Il metodo richiama il codice gestito mediante un'istruzione di restituzione. Nel codice gestito successivo viene eseguita l'uscita.|  
|`CODE_INVOKE_KIND_TAILCALL`|Questo metodo richiama il codice gestito mediante una chiamata tail. L'esecuzione passo-passo e l'esecuzione di istruzioni per tutte le istruzioni della chiamata vengono completate nel codice gestito.|  
  
## <a name="remarks"></a>Note  
 Questa enumerazione viene utilizzata dal metodo [Metodo icordebugprocess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) per fornire informazioni sull'esecuzione del codice gestito.  
  
> [!NOTE]
> Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
