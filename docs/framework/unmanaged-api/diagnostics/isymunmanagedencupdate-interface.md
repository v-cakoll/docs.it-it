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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 634716b36a0e5826cd7667a9ae948e8172724a1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630866"
---
# <a name="isymunmanagedencupdate-interface"></a>Interfaccia ISymUnmanagedENCUpdate
Fornisce funzioni per la funzionalità Modifica e continuazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetLocalVariableCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|Ottiene il numero di variabili locali.|  
|[Metodo GetLocalVariables](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|Ottiene le variabili locali.|  
|[Metodo InitializeForEnc](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|Consente i limiti del metodo deve essere calcolata prima della prima chiamata per il [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) (metodo).|  
|[Metodo UpdateMethodLines](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono spostati in modo indipendente. Valore delta di ogni istruzione è consentito.|  
|[Metodo UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) del database, condizione che le informazioni sulla riga soddisfa i requisiti. Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe della funzione.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
