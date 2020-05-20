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
ms.openlocfilehash: 5a26de2a8f5439b7c81560927c991d449e57b76c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441591"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="80680-102">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="80680-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="80680-103">Estende l'interfaccia del gestore di associazione dei simboli.</span><span class="sxs-lookup"><span data-stu-id="80680-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="80680-104">Ottenere questa interfaccia chiamando `QueryInterface` su un oggetto che implementa l' `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="80680-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="80680-105">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="80680-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80680-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="80680-106">Methods</span></span>  
  
|<span data-ttu-id="80680-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="80680-107">Method</span></span>|<span data-ttu-id="80680-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80680-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80680-109">Metodo GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="80680-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="80680-110">Consente all'utente di implementare o fornire tramite callback o `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni della directory di debug dalla memoria</span><span class="sxs-lookup"><span data-stu-id="80680-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80680-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80680-111">Requirements</span></span>  
 <span data-ttu-id="80680-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="80680-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80680-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80680-113">See also</span></span>

- [<span data-ttu-id="80680-114">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="80680-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="80680-115">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="80680-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="80680-116">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="80680-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
