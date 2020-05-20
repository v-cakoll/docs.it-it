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
ms.openlocfilehash: 8a4fbb40ec2426d000628fbd6d5f0241d3152c18
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441669"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="35be5-102">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="35be5-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="35be5-103">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="35be5-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="35be5-104">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="35be5-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35be5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="35be5-105">Methods</span></span>  
  
|<span data-ttu-id="35be5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="35be5-106">Method</span></span>|<span data-ttu-id="35be5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35be5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35be5-108">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="35be5-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="35be5-109">Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="35be5-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="35be5-110">Fornisce una ricerca più ampia rispetto al metodo [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35be5-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35be5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35be5-111">Requirements</span></span>  
 <span data-ttu-id="35be5-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="35be5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35be5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35be5-113">See also</span></span>

- [<span data-ttu-id="35be5-114">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="35be5-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="35be5-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="35be5-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="35be5-116">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="35be5-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
