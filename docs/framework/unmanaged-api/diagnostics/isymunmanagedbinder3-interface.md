---
title: Interfaccia ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157508"
---
# <a name="isymunmanagedbinder3-interface"></a>Interfaccia ISymUnmanagedBinder3
Estende l'interfaccia dello strumento di associazione di simboli. Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il `ISymUnmanagedBinder` interfaccia.  
  
> [!IMPORTANT]
>  È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|Consente di implementare o fornire mediante callback un' `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory di Debug dalla memoria|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Interfaccia ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [Interfaccia ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
