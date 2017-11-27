---
title: Interfaccia ISymUnmanagedWriter2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2
helpviewer_keywords: ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd297a8ee0172f1624e6983de9bc9bf25bd86621
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2-interface"></a>Interfaccia ISymUnmanagedWriter2
Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti. Questa interfaccia estende il [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interfaccia.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[DefineConstant2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|Definisce un nome per un valore costante.|  
|[DefineGlobalVariable2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|Definisce una singola variabile globale.|  
|[DefineLocalVariable2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|Definisce una singola variabile nell'ambito lessicale corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedWriter (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [ISymUnmanagedWriter3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
