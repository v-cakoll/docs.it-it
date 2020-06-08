---
title: Interfaccia ISymUnmanagedBinder2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: f6155eb777b5071ff522af4f27d5fb2d73aa25ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501833"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="e2bf8-102">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="e2bf8-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="e2bf8-103">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e2bf8-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e2bf8-104">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e2bf8-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2bf8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e2bf8-105">Methods</span></span>  
  
|<span data-ttu-id="e2bf8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e2bf8-106">Method</span></span>|<span data-ttu-id="e2bf8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2bf8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2bf8-108">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="e2bf8-108">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="e2bf8-109">Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="e2bf8-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="e2bf8-110">Fornisce una ricerca più ampia rispetto al metodo [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e2bf8-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2bf8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2bf8-111">Requirements</span></span>  
 <span data-ttu-id="e2bf8-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e2bf8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bf8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2bf8-113">See also</span></span>

- [<span data-ttu-id="e2bf8-114">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e2bf8-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e2bf8-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="e2bf8-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="e2bf8-116">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="e2bf8-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
