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
ms.openlocfilehash: 49949989a48be13bcb70b27e47407d907b284670
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494954"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="d217b-102">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="d217b-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="d217b-103">Rappresenta un raccoglitore di simboli per codice non gestito ed estende la [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d217b-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d217b-104">È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="d217b-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d217b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d217b-105">Methods</span></span>  
  
|<span data-ttu-id="d217b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d217b-106">Method</span></span>|<span data-ttu-id="d217b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d217b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d217b-108">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="d217b-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="d217b-109">Data un'interfaccia di metadati e un nome di file, restituisce il valore corretto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaccia che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="d217b-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="d217b-110">Fornisce una ricerca più estesa rispetto al [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d217b-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d217b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d217b-111">Requirements</span></span>  
 <span data-ttu-id="d217b-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d217b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d217b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d217b-113">See also</span></span>
- [<span data-ttu-id="d217b-114">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d217b-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d217b-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="d217b-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="d217b-116">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="d217b-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
