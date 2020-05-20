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
ms.openlocfilehash: f4f925282d65cd9cbc8eb1c8825f358602de68ed
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441695"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="87f8f-102">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="87f8f-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="87f8f-103">Rappresenta uno strumento di associazione di simboli per il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="87f8f-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="87f8f-104">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="87f8f-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87f8f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="87f8f-105">Methods</span></span>  
  
|<span data-ttu-id="87f8f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="87f8f-106">Method</span></span>|<span data-ttu-id="87f8f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87f8f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87f8f-108">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="87f8f-108">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="87f8f-109">Data un'interfaccia di metadati e un nome file, restituisce la struttura [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="87f8f-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="87f8f-110">Metodo GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="87f8f-110">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="87f8f-111">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce la struttura [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug dall'archivio dei simboli specificato.</span><span class="sxs-lookup"><span data-stu-id="87f8f-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87f8f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87f8f-112">Requirements</span></span>  
 <span data-ttu-id="87f8f-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="87f8f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f8f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87f8f-114">See also</span></span>

- [<span data-ttu-id="87f8f-115">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="87f8f-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="87f8f-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="87f8f-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="87f8f-117">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="87f8f-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
