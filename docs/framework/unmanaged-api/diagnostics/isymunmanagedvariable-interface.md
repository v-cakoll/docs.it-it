---
title: Interfaccia ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797481"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="9446b-102">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="9446b-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="9446b-103">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="9446b-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9446b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9446b-104">Methods</span></span>  
  
|<span data-ttu-id="9446b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9446b-105">Method</span></span>|<span data-ttu-id="9446b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9446b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9446b-107">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="9446b-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="9446b-108">Ottiene il primo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="9446b-109">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9446b-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="9446b-110">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="9446b-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="9446b-111">Ottiene il secondo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="9446b-112">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9446b-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="9446b-113">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="9446b-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="9446b-114">Ottiene il terzo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="9446b-115">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9446b-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="9446b-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="9446b-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="9446b-117">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="9446b-118">Metodo GetAttributes</span><span class="sxs-lookup"><span data-stu-id="9446b-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="9446b-119">Ottiene i flag di attributo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="9446b-120">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="9446b-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="9446b-121">Ottiene l'offset finale della variabile all'interno di relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9446b-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="9446b-122">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="9446b-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="9446b-123">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="9446b-124">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="9446b-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="9446b-125">Ottiene la firma della variabile.</span><span class="sxs-lookup"><span data-stu-id="9446b-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="9446b-126">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="9446b-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="9446b-127">Ottiene l'offset di inizio di questa variabile all'interno di relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9446b-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9446b-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9446b-128">Requirements</span></span>  
 <span data-ttu-id="9446b-129">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9446b-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9446b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9446b-130">See also</span></span>

- [<span data-ttu-id="9446b-131">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9446b-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
