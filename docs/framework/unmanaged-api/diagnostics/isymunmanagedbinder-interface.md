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
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="d8b8b-102">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="d8b8b-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="d8b8b-103">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="d8b8b-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d8b8b-104">È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="d8b8b-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8b8b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d8b8b-105">Methods</span></span>  
  
|<span data-ttu-id="d8b8b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d8b8b-106">Method</span></span>|<span data-ttu-id="d8b8b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8b8b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8b8b-108">GetReaderForFile (metodo)</span><span class="sxs-lookup"><span data-stu-id="d8b8b-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="d8b8b-109">Data un'interfaccia di metadati e un nome di file, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che verrà letti i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="d8b8b-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="d8b8b-110">GetReaderFromStream (metodo)</span><span class="sxs-lookup"><span data-stu-id="d8b8b-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="d8b8b-111">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.</span><span class="sxs-lookup"><span data-stu-id="d8b8b-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8b8b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8b8b-112">Requirements</span></span>  
 <span data-ttu-id="d8b8b-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8b8b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b8b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b8b-114">See Also</span></span>  
 [<span data-ttu-id="d8b8b-115">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d8b8b-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="d8b8b-116">ISymUnmanagedBinder2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d8b8b-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="d8b8b-117">ISymUnmanagedBinder3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d8b8b-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
