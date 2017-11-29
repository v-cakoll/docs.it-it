---
title: Interfaccia ISymUnmanagedBinder2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2 Interface
helpviewer_keywords: ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c276f0abedf4ccab92770af649a8dd0afb6d39d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder2-interface"></a>Interfaccia ISymUnmanagedBinder2
Rappresenta un raccoglitore di simboli per codice non gestito ed estende il [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interfaccia.  
  
> [!IMPORTANT]
>  È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetReaderForFile2 (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia che verrà letti i simboli di debug associati al modulo. Esegue una ricerca più completa rispetto di [ISymUnmanagedBinder::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce dell'archivio dei simboli di diagnostica](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [Interfaccia ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [ISymUnmanagedBinder3 (interfaccia)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
