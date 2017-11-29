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
ms.openlocfilehash: 5061ce28c4a09f445267c99420bf1942d99076bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="c8bce-102">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="c8bce-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="c8bce-103">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="c8bce-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c8bce-104">È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="c8bce-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8bce-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c8bce-105">Methods</span></span>  
  
|<span data-ttu-id="c8bce-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c8bce-106">Method</span></span>|<span data-ttu-id="c8bce-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8bce-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8bce-108">GetReaderForFile (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8bce-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="c8bce-109">Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Struttura che verrà letti i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="c8bce-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="c8bce-110">GetReaderFromStream (metodo)</span><span class="sxs-lookup"><span data-stu-id="c8bce-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="c8bce-111">Dato un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.</span><span class="sxs-lookup"><span data-stu-id="c8bce-111">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8bce-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8bce-112">Requirements</span></span>  
 <span data-ttu-id="c8bce-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c8bce-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bce-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8bce-114">See Also</span></span>  
 [<span data-ttu-id="c8bce-115">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c8bce-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="c8bce-116">ISymUnmanagedBinder2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c8bce-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="c8bce-117">ISymUnmanagedBinder3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c8bce-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
