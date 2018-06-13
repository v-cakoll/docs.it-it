---
title: Interfaccia ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427431"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="7819e-102">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7819e-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="7819e-103">Rappresenta un metodo all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="7819e-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="7819e-104">Questa interfaccia fornisce l'accesso solo gli attributi relativi ai simboli di un metodo, anziché gli attributi relativi al tipo.</span><span class="sxs-lookup"><span data-stu-id="7819e-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7819e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7819e-105">Methods</span></span>  
  
|<span data-ttu-id="7819e-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7819e-106">Method</span></span>|<span data-ttu-id="7819e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7819e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7819e-108">Metodo GetNamespace</span><span class="sxs-lookup"><span data-stu-id="7819e-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="7819e-109">Ottiene lo spazio dei nomi all'interno del quale è definito questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="7819e-110">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="7819e-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="7819e-111">Restituisce l'offset all'interno del metodo che corrisponde a una posizione specifica all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="7819e-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="7819e-112">Metodo GetParameters</span><span class="sxs-lookup"><span data-stu-id="7819e-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="7819e-113">Ottiene i parametri per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="7819e-114">Metodo GetRanges</span><span class="sxs-lookup"><span data-stu-id="7819e-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="7819e-115">Data una posizione in un documento, restituisce una matrice di coppie di offset iniziali e finali che corrispondono agli intervalli di Microsoft intermediate language (MSIL) che la posizione all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="7819e-116">Metodo GetRootScope</span><span class="sxs-lookup"><span data-stu-id="7819e-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="7819e-117">Ottiene l'ambito lessicale di primo livello all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="7819e-118">Questo ambito racchiude l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="7819e-119">Metodo GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="7819e-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="7819e-120">Ottiene l'ambito lessicale di maggiore inclusione all'interno del metodo che racchiude un offset specificato.</span><span class="sxs-lookup"><span data-stu-id="7819e-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="7819e-121">Metodo GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="7819e-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="7819e-122">Ottiene il numero di punti di sequenza all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="7819e-123">Metodo GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="7819e-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="7819e-124">Ottiene tutti i punti di sequenza all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="7819e-125">Metodo GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="7819e-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="7819e-126">Ottiene le posizioni di documento di inizio e di fine per l'origine di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="7819e-127">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="7819e-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="7819e-128">Restituisce il token di metadati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7819e-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7819e-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7819e-129">Requirements</span></span>  
 <span data-ttu-id="7819e-130">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7819e-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7819e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7819e-131">See Also</span></span>  
 [<span data-ttu-id="7819e-132">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7819e-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
