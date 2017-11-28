---
title: Interfaccia ISymUnmanagedBinder3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder3 Interface
helpviewer_keywords: ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: df5cd6d4015fad1baf98909ee9cc923cd9bce05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="903b2-102">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="903b2-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="903b2-103">Estende l'interfaccia del Raccoglitore di simboli.</span><span class="sxs-lookup"><span data-stu-id="903b2-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="903b2-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="903b2-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="903b2-105">È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="903b2-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="903b2-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="903b2-106">Methods</span></span>  
  
|<span data-ttu-id="903b2-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="903b2-107">Method</span></span>|<span data-ttu-id="903b2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="903b2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="903b2-109">GetReaderFromCallback (metodo)</span><span class="sxs-lookup"><span data-stu-id="903b2-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="903b2-110">Consente di implementare o fornire mediante callback un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory Debug dalla memoria</span><span class="sxs-lookup"><span data-stu-id="903b2-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="903b2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="903b2-111">Requirements</span></span>  
 <span data-ttu-id="903b2-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="903b2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903b2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="903b2-113">See Also</span></span>  
 [<span data-ttu-id="903b2-114">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="903b2-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="903b2-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="903b2-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="903b2-116">ISymUnmanagedBinder2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="903b2-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
