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
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="8a194-102">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="8a194-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="8a194-103">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="8a194-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8a194-104">È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="8a194-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a194-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8a194-105">Methods</span></span>  
  
|<span data-ttu-id="8a194-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="8a194-106">Method</span></span>|<span data-ttu-id="8a194-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a194-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a194-108">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="8a194-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="8a194-109">Data un'interfaccia di metadati e un nome di file, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che verrà letti i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="8a194-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="8a194-110">Metodo GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="8a194-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="8a194-111">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.</span><span class="sxs-lookup"><span data-stu-id="8a194-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a194-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a194-112">Requirements</span></span>  
 <span data-ttu-id="8a194-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8a194-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a194-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a194-114">See Also</span></span>  
 [<span data-ttu-id="8a194-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="8a194-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="8a194-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="8a194-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="8a194-117">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="8a194-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
