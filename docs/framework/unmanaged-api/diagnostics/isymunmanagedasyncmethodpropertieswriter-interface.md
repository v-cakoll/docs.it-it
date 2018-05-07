---
title: Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ec66e0064a8d6e8d4664dd8c727aa87621cfd8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter
Consente di definire le informazioni sul metodo async facoltativo per ogni simbolo del metodo. Utilizzare sempre con un metodo di aperto. vale a dire, tra le chiamate al [OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) e [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Metodi  
 Per l'interfaccia sono disponibili i seguenti metodi:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definire un gruppo di async await operazioni nel metodo corrente.<br /><br /> Istruzione return di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield. Ogni `breakpointMethod` / `breakpointOffset` coppia identifica dove riprende l'operazione asincrona, potrebbe essere in un altro metodo.|  
|[Metodo DefineCatchHandlerILOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.<br /><br /> Offset IL di catch generato viene utilizzata dal debugger per gestire catch come se fosse il codice non utente, anche se può verificarsi in un metodo del codice utente. In particolare, viene utilizzato in risposta a un **CatchHandlerFound** evento dell'eccezione.|  
|[Metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Imposta il metodo di avvio che avvia l'operazione asincrona.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
