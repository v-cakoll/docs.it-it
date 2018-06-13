---
title: Interfaccia ISymUnmanagedBinder
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bbdc4b1f15c8dbb154ed7b967bb21c61d11782a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425552"
---
# <a name="isymunmanagedbinder-interface"></a>Interfaccia ISymUnmanagedBinder
Rappresenta un raccoglitore di simboli per codice non gestito.  
  
> [!IMPORTANT]
>  È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|Data un'interfaccia di metadati e un nome di file, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che verrà letti i simboli di debug associati al modulo.|  
|[Metodo GetReaderFromStream](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [Interfaccia ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [Interfaccia ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
