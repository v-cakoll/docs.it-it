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
ms.openlocfilehash: 29501eeb6085dbc235112d98e8099fcfa4565000
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427795"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="2d16d-102">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="2d16d-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="2d16d-103">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2d16d-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d16d-104">È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="2d16d-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d16d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="2d16d-105">Methods</span></span>  
  
|<span data-ttu-id="2d16d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="2d16d-106">Method</span></span>|<span data-ttu-id="2d16d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d16d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d16d-108">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="2d16d-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="2d16d-109">Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia che verrà letti i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="2d16d-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="2d16d-110">Esegue una ricerca più completa rispetto di [ISymUnmanagedBinder::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="2d16d-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d16d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d16d-111">Requirements</span></span>  
 <span data-ttu-id="2d16d-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d16d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d16d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d16d-113">See Also</span></span>  
 [<span data-ttu-id="2d16d-114">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="2d16d-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="2d16d-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="2d16d-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="2d16d-116">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="2d16d-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
