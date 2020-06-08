---
title: Interfaccia ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501742"
---
# <a name="isymunmanagedencupdate-interface"></a>Interfaccia ISymUnmanagedENCUpdate
Fornisce funzioni per la funzionalità di modifica e continuazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetLocalVariableCount](isymunmanagedencupdate-getlocalvariablecount-method.md)|Ottiene il numero di variabili locali.|  
|[Metodo GetLocalVariables](isymunmanagedencupdate-getlocalvariables-method.md)|Ottiene le variabili locali.|  
|[Metodo InitializeForEnc](isymunmanagedencupdate-initializeforenc-method.md)|Consente il calcolo dei limiti del metodo prima della prima chiamata al metodo [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) .|  
|[Metodo UpdateMethodLines](isymunmanagedencupdate-updatemethodlines-method.md)|Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono state spostate in modo indipendente. È consentito un Delta per ogni istruzione.|  
|[Metodo UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md)|Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso del database di programma (PDB), purché le informazioni sulla riga soddisfino i requisiti. Le informazioni sulla riga corrette possono essere determinate con le informazioni sulla riga PDB precedenti e un Delta per tutte le righe nella funzione.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](diagnostics-symbol-store-interfaces.md)
