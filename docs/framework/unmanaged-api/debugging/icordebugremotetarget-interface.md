---
title: Interfaccia ICorDebugRemoteTarget
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: 97c4e6d3c9de7dcb8d399a956a4a58c49ca6e3b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131877"
---
# <a name="icordebugremotetarget-interface"></a>Interfaccia ICorDebugRemoteTarget
Fornisce i metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR (Common Language Runtime).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ICorDebugRemoteTarget::GetHostName](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|Restituisce il nome host o l'indirizzo IP di un computer remoto.|  
  
## <a name="remarks"></a>Note  
 Il debug in modalità mista (cioè codice gestito e nativo) non è supportato né da Windows 95, Windows 98 o Windows ME né dalle piattaforme diverse da x86 (ad esempio IA-64 e AMD64).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl  
  
 **Libreria:** : corguids. lib  
  
 **Versioni .NET Framework:** 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
