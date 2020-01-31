---
title: Interfaccia ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793638"
---
# <a name="iclrdebugging-interface"></a>Interfaccia ICLRDebugging
Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)|Ottiene l'interfaccia "ICorDebugProcess" che corrisponde a un modulo Common Language Runtime (CLR) caricato nel processo.|  
|[Metodo CanUnloadNow](iclrdebugging-canunloadnow-method.md)|Determina se una libreria fornita da un'interfaccia [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) è ancora in uso o può essere scaricata.|  
  
## <a name="remarks"></a>Note  
 È possibile ottenere un'istanza dell'interfaccia `ICLRDebugging` tramite la funzione [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
