---
title: Interfaccia ISymUnmanagedBinder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 00b0b5ee330a606ae7417185a804f3d37ab6664a
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbinder-interface"></a>Interfaccia ISymUnmanagedBinder
Rappresenta un raccoglitore di simboli per codice non gestito.  
  
> [!IMPORTANT]
>  È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetReaderForFile (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|Data un'interfaccia di metadati e un nome di file, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che verrà letti i simboli di debug associati al modulo.|  
|[GetReaderFromStream (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedBinder2 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [ISymUnmanagedBinder3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
