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
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615124"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="7ea55-102">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7ea55-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="7ea55-103">Rappresenta un metodo all'interno dell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="7ea55-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="7ea55-104">Questa interfaccia consente di accedere solo agli attributi relativi ai simboli di un metodo, anziché agli attributi correlati al tipo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ea55-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7ea55-105">Methods</span></span>  
  
|<span data-ttu-id="7ea55-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7ea55-106">Method</span></span>|<span data-ttu-id="7ea55-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ea55-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ea55-108">Metodo GetNamespace</span><span class="sxs-lookup"><span data-stu-id="7ea55-108">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="7ea55-109">Ottiene lo spazio dei nomi in cui è definito il metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="7ea55-110">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="7ea55-110">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="7ea55-111">Restituisce l'offset all'interno di questo metodo che corrisponde a una posizione specificata all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="7ea55-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="7ea55-112">Metodo GetParameters</span><span class="sxs-lookup"><span data-stu-id="7ea55-112">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="7ea55-113">Ottiene i parametri per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="7ea55-114">Metodo GetRanges</span><span class="sxs-lookup"><span data-stu-id="7ea55-114">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="7ea55-115">Data una posizione in un documento, restituisce una matrice di coppie di offset di inizio e di fine che corrispondono agli intervalli di MSIL (Microsoft Intermediate Language) che la posizione copre all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="7ea55-116">Metodo GetRootScope</span><span class="sxs-lookup"><span data-stu-id="7ea55-116">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="7ea55-117">Ottiene l'ambito lessicale radice all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="7ea55-118">Questo ambito racchiude l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="7ea55-119">Metodo GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="7ea55-119">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="7ea55-120">Ottiene l'ambito lessicale di maggiore inclusione all'interno di questo metodo che racchiude l'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="7ea55-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="7ea55-121">Metodo GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="7ea55-121">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="7ea55-122">Ottiene il conteggio dei punti di sequenza all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="7ea55-123">Metodo GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="7ea55-123">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="7ea55-124">Ottiene tutti i punti di sequenza all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="7ea55-125">Metodo GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="7ea55-125">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="7ea55-126">Ottiene le posizioni del documento iniziale e finale per l'origine di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="7ea55-127">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="7ea55-127">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="7ea55-128">Restituisce il token di metadati per il metodo.</span><span class="sxs-lookup"><span data-stu-id="7ea55-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ea55-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ea55-129">Requirements</span></span>  
 <span data-ttu-id="7ea55-130">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7ea55-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea55-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ea55-131">See also</span></span>

- [<span data-ttu-id="7ea55-132">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7ea55-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
