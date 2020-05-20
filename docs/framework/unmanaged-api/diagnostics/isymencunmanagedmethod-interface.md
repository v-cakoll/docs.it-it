---
title: Interfaccia ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441877"
---
# <a name="isymencunmanagedmethod-interface"></a>Interfaccia ISymENCUnmanagedMethod
Fornisce informazioni per la funzionalità di modifica e continuazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetDocumentsForMethod](isymencunmanagedmethod-getdocumentsformethod-method.md)|Ottiene i documenti in cui questo metodo contiene righe.|  
|[Metodo GetDocumentsForMethodCount](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Ottiene il numero di documenti in cui questo metodo contiene righe.|  
|[Metodo GetFileNameFromOffset](isymencunmanagedmethod-getfilenamefromoffset-method.md)|Ottiene il nome file per la riga associata a un offset.|  
|[Metodo GetLineFromOffset](isymencunmanagedmethod-getlinefromoffset-method.md)|Ottiene le informazioni sulla riga associate a un offset.|  
|[Metodo GetSourceExtentInDocument](isymencunmanagedmethod-getsourceextentindocument-method.md)|Ottiene la riga iniziale più piccola e la riga finale più grande per il metodo in un documento specifico.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
