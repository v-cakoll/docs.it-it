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
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445983"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="e3d4d-102">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="e3d4d-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="e3d4d-103">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3d4d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e3d4d-104">Methods</span></span>  
  
|<span data-ttu-id="e3d4d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e3d4d-105">Method</span></span>|<span data-ttu-id="e3d4d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3d4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3d4d-107">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="e3d4d-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="e3d4d-108">Gets the first address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="e3d4d-109">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="e3d4d-110">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="e3d4d-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="e3d4d-111">Gets the second address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="e3d4d-112">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="e3d4d-113">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="e3d4d-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="e3d4d-114">Gets the third address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="e3d4d-115">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="e3d4d-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="e3d4d-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="e3d4d-117">Gets the kind of address of this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="e3d4d-118">Metodo GetAttributes</span><span class="sxs-lookup"><span data-stu-id="e3d4d-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="e3d4d-119">Gets the attribute flags for this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="e3d4d-120">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="e3d4d-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="e3d4d-121">Gets the end offset of this variable within its parent.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="e3d4d-122">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="e3d4d-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="e3d4d-123">Gets the name of this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="e3d4d-124">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="e3d4d-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="e3d4d-125">Gets the signature of this variable.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="e3d4d-126">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="e3d4d-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="e3d4d-127">Gets the start offset of this variable within its parent.</span><span class="sxs-lookup"><span data-stu-id="e3d4d-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3d4d-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3d4d-128">Requirements</span></span>  
 <span data-ttu-id="e3d4d-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e3d4d-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d4d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3d4d-130">See also</span></span>

- [<span data-ttu-id="e3d4d-131">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e3d4d-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
