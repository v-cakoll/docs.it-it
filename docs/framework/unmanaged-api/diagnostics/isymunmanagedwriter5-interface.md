---
title: Interfaccia ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: bdc630c3c94c7d03b736efa0a95665f10aac7c6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609430"
---
# <a name="isymunmanagedwriter5-interface"></a>Interfaccia ISymUnmanagedWriter5
Interfaccia Metodo ISymUnmanagedWriter5.  
  
## <a name="syntax"></a>Sintassi  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>Metodi  
 Per l'interfaccia sono disponibili i seguenti metodi:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine. Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.|  
|[Metodo MapTokenToSourceSpan](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|Esegue il mapping del token di metadati specificato all'intervallo di righe di origine specificato nel file di origine specificato.<br /><br /> Deve essere chiamato tra le chiamate al [Metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e al [Metodo CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).|  
|[Metodo OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|Aprire una sezione di dati personalizzata speciale per creare informazioni sul mapping di intervalli da token a origine in. L'apertura di questa sezione quando un metodo è già aperto o viceversa è un errore.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedWriter4](isymunmanagedwriter4-interface.md)
