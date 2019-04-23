---
title: Interfaccia ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157508"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="7e2d0-102">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="7e2d0-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="7e2d0-103">Estende l'interfaccia dello strumento di associazione di simboli.</span><span class="sxs-lookup"><span data-stu-id="7e2d0-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="7e2d0-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7e2d0-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7e2d0-105">È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="7e2d0-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e2d0-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="7e2d0-106">Methods</span></span>  
  
|<span data-ttu-id="7e2d0-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="7e2d0-107">Method</span></span>|<span data-ttu-id="7e2d0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e2d0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e2d0-109">Metodo GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="7e2d0-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="7e2d0-110">Consente di implementare o fornire mediante callback un' `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory di Debug dalla memoria</span><span class="sxs-lookup"><span data-stu-id="7e2d0-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e2d0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e2d0-111">Requirements</span></span>  
 <span data-ttu-id="7e2d0-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e2d0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2d0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e2d0-113">See also</span></span>

- [<span data-ttu-id="7e2d0-114">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7e2d0-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="7e2d0-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="7e2d0-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="7e2d0-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="7e2d0-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
