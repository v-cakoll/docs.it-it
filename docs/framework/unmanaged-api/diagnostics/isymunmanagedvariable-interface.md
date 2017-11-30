---
title: Interfaccia ISymUnmanagedVariable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable
helpviewer_keywords: ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c32d5b66c575a21b4d390cff560b71f93aa31927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="90c9e-102">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="90c9e-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="90c9e-103">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="90c9e-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90c9e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="90c9e-104">Methods</span></span>  
  
|<span data-ttu-id="90c9e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="90c9e-105">Method</span></span>|<span data-ttu-id="90c9e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90c9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90c9e-107">GetAddressField1 (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="90c9e-108">Ottiene il primo campo di indirizzo per la variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="90c9e-109">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="90c9e-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="90c9e-110">GetAddressField2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="90c9e-111">Ottiene il secondo campo dell'indirizzo per la variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="90c9e-112">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="90c9e-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="90c9e-113">GetAddressField3 (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="90c9e-114">Ottiene il terzo campo indirizzo per la variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="90c9e-115">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="90c9e-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="90c9e-116">GetAddressKind (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="90c9e-117">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="90c9e-118">GetAttributes (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="90c9e-119">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="90c9e-120">GetEndOffset (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="90c9e-121">Ottiene l'offset finale di questa variabile all'interno del relativo padre.</span><span class="sxs-lookup"><span data-stu-id="90c9e-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="90c9e-122">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="90c9e-123">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="90c9e-124">GetSignature (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="90c9e-125">Ottiene la firma di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="90c9e-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="90c9e-126">GetStartOffset (metodo)</span><span class="sxs-lookup"><span data-stu-id="90c9e-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="90c9e-127">Ottiene l'offset di inizio di questa variabile all'interno del relativo padre.</span><span class="sxs-lookup"><span data-stu-id="90c9e-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90c9e-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90c9e-128">Requirements</span></span>  
 <span data-ttu-id="90c9e-129">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="90c9e-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c9e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90c9e-130">See Also</span></span>  
 [<span data-ttu-id="90c9e-131">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="90c9e-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
