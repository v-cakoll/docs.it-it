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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157508"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="34224-102">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="34224-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="34224-103">Estende l'interfaccia dello strumento di associazione di simboli.</span><span class="sxs-lookup"><span data-stu-id="34224-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="34224-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="34224-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34224-105">È un rischio per la sicurezza per aprire un file di programma (PDB) del database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="34224-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34224-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="34224-106">Methods</span></span>  
  
|<span data-ttu-id="34224-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="34224-107">Method</span></span>|<span data-ttu-id="34224-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34224-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34224-109">Metodo GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="34224-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="34224-110">Consente di implementare o fornire mediante callback un' `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory di Debug dalla memoria</span><span class="sxs-lookup"><span data-stu-id="34224-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34224-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34224-111">Requirements</span></span>  
 <span data-ttu-id="34224-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="34224-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34224-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34224-113">See also</span></span>

- [<span data-ttu-id="34224-114">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="34224-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="34224-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="34224-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="34224-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="34224-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
