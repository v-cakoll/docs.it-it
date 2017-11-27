---
title: Interfaccia ISymUnmanagedScope2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2
helpviewer_keywords: ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eed6061c8108fcf91f8ac1ac9ff139da426f0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope2-interface"></a>Interfaccia ISymUnmanagedScope2
Rappresenta un ambito lessicale in un metodo. Questa interfaccia estende il [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaccia con metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetConstantCount (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|Ottiene un conteggio delle costanti definite in questo ambito.|  
|[GetConstants (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|Ottiene le costanti locali definite in questo ambito.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedScope (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
