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
ms.openlocfilehash: f23df98abc5355f0b25d7253b5f2ae808b3446a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449366"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="ca3bc-102">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="ca3bc-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="ca3bc-103">Rappresenta uno strumento di associazione di simboli per il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="ca3bc-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ca3bc-104">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ca3bc-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca3bc-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ca3bc-105">Methods</span></span>  
  
|<span data-ttu-id="ca3bc-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ca3bc-106">Method</span></span>|<span data-ttu-id="ca3bc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca3bc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca3bc-108">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="ca3bc-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="ca3bc-109">Data un'interfaccia di metadati e un nome file, restituisce la struttura [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="ca3bc-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="ca3bc-110">Metodo GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="ca3bc-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="ca3bc-111">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce la struttura [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug dall'archivio dei simboli specificato.</span><span class="sxs-lookup"><span data-stu-id="ca3bc-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca3bc-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca3bc-112">Requirements</span></span>  
 <span data-ttu-id="ca3bc-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ca3bc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3bc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca3bc-114">See also</span></span>

- [<span data-ttu-id="ca3bc-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ca3bc-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ca3bc-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="ca3bc-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="ca3bc-117">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="ca3bc-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
