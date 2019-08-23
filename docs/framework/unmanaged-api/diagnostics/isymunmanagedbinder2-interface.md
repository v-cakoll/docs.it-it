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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9fbb8364fb967e739eb9807b26cbc65f0ebec1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944185"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="c7b63-102">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="c7b63-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="c7b63-103">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c7b63-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c7b63-104">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c7b63-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7b63-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c7b63-105">Methods</span></span>  
  
|<span data-ttu-id="c7b63-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c7b63-106">Method</span></span>|<span data-ttu-id="c7b63-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c7b63-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7b63-108">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="c7b63-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="c7b63-109">Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="c7b63-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="c7b63-110">Fornisce una ricerca più ampia rispetto al metodo [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c7b63-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7b63-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7b63-111">Requirements</span></span>  
 <span data-ttu-id="c7b63-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c7b63-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b63-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7b63-113">See also</span></span>

- [<span data-ttu-id="c7b63-114">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c7b63-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c7b63-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="c7b63-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="c7b63-116">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="c7b63-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
