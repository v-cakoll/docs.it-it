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
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940062"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="25cae-102">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="25cae-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="25cae-103">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="25cae-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="25cae-104">È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="25cae-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25cae-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="25cae-105">Methods</span></span>  
  
|<span data-ttu-id="25cae-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="25cae-106">Method</span></span>|<span data-ttu-id="25cae-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25cae-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25cae-108">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="25cae-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="25cae-109">Data un'interfaccia di metadati e un nome di file, restituisce il valore corretto [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="25cae-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="25cae-110">Metodo GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="25cae-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="25cae-111">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il valore corretto [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che leggerà il debug di simboli dall'archivio di simbolo specificato.</span><span class="sxs-lookup"><span data-stu-id="25cae-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25cae-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25cae-112">Requirements</span></span>  
 <span data-ttu-id="25cae-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="25cae-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cae-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25cae-114">See also</span></span>

- [<span data-ttu-id="25cae-115">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="25cae-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="25cae-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="25cae-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="25cae-117">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="25cae-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
