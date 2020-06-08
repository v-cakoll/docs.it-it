---
title: Interfaccia ISymUnmanagedAsyncMethod
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 448ed719331469dce8f15500f14d5c1b0707ecf7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504452"
---
# <a name="isymunmanagedasyncmethod-interface"></a>Interfaccia ISymUnmanagedAsyncMethod
Questa interfaccia è il complemento di lettura per l' [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a>Metodi  
 Per l'interfaccia sono disponibili i seguenti metodi:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAsyncStepInfo](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|Vedere il [Metodo DefineAsyncStepInfo](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[Metodo GetAsyncStepInfoCount](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|Vedere il [Metodo DefineAsyncStepInfo](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).|  
|[Metodo GetCatchHandlerILOffset](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|Vedere il [Metodo DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[Metodo GetKickoffMethod](isymunmanagedasyncmethod-getkickoffmethod-method.md)|Vedere il [Metodo DefineKickoffMethod](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).|  
|[Metodo HasCatchHandlerILOffset](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|Vedere il [Metodo DefineCatchHandlerILOffset](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).|  
|[Metodo IsAsyncMethod](isymunmanagedasyncmethod-isasyncmethod-method.md)|Verifica se il metodo contiene informazioni asincrone o meno.<br /><br /> Se questo metodo restituisce `FALSE` , non è valido chiamare altri metodi in questa interfaccia. `E_UNEXPECTED`In questo caso verranno restituiti tutti.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
