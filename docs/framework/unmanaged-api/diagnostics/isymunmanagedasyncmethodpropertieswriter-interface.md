---
title: Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 04876483fd42e3f6e55222416fd0747891734a52
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501859"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter
Consente di definire informazioni facoltative sul metodo asincrono per ogni simbolo di metodo. Usare sempre con un metodo aperto; ovvero tra le chiamate al [Metodo OpenMethod](isymunmanagedwriter-openmethod-method.md) e il [Metodo CloseMethod](isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Metodi  
 Per l'interfaccia sono disponibili i seguenti metodi:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineAsyncStepInfo](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definire un gruppo di operazioni di attesa asincrone nel metodo corrente.<br /><br /> Ogni offset yield corrisponde a un'istruzione return di await, che identifica un potenziale rendimento. Ogni `breakpointMethod` / `breakpointOffset` coppia identifica la posizione in cui verrà ripresa l'operazione asincrona. potrebbe trovarsi in un metodo diverso.|  
|[Metodo DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Imposta l'offset il per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono.<br /><br /> L'offset il dell'oggetto catch generato viene utilizzato dal debugger per gestire l'oggetto Catch come se fosse un codice non utente, anche se potrebbe verificarsi in un metodo del codice utente. In particolare, viene usato in risposta a un evento di eccezione **CatchHandlerFound** .|  
|[Metodo DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Imposta il metodo iniziale che avvia l'operazione asincrona.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
