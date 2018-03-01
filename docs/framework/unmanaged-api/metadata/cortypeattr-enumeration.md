---
title: Enumerazione CorTypeAttr
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 501488c0ac03ebf508145572ed73163d7940bfbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="03785-102">Enumerazione CorTypeAttr</span><span class="sxs-lookup"><span data-stu-id="03785-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="03785-103">Contiene valori che indicano i metadati del tipo.</span><span class="sxs-lookup"><span data-stu-id="03785-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03785-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03785-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="03785-105">Membri</span><span class="sxs-lookup"><span data-stu-id="03785-105">Members</span></span>  
  
|<span data-ttu-id="03785-106">Membro</span><span class="sxs-lookup"><span data-stu-id="03785-106">Member</span></span>|<span data-ttu-id="03785-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03785-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="03785-108">Usato per informazioni sulla visibilità del tipo.</span><span class="sxs-lookup"><span data-stu-id="03785-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="03785-109">Specifica che il tipo non è in ambito pubblico.</span><span class="sxs-lookup"><span data-stu-id="03785-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="03785-110">Specifica che il tipo sia in ambito pubblico.</span><span class="sxs-lookup"><span data-stu-id="03785-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="03785-111">Specifica che il tipo è annidato e con visibilità pubblica.</span><span class="sxs-lookup"><span data-stu-id="03785-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="03785-112">Specifica che il tipo è annidato e con visibilità privata.</span><span class="sxs-lookup"><span data-stu-id="03785-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="03785-113">Specifica che il tipo è annidato e con visibilità famiglia.</span><span class="sxs-lookup"><span data-stu-id="03785-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="03785-114">Specifica che il tipo è annidato e con visibilità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="03785-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="03785-115">Specifica che il tipo è annidato e con visibilità famiglia e assembly.</span><span class="sxs-lookup"><span data-stu-id="03785-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="03785-116">Specifica che il tipo è annidato e con visibilità famiglia o assembly.</span><span class="sxs-lookup"><span data-stu-id="03785-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="03785-117">Ottiene informazioni sul layout per il tipo.</span><span class="sxs-lookup"><span data-stu-id="03785-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="03785-118">Specifica che i campi di questo tipo sono disposti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="03785-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="03785-119">Specifica che i campi di questo tipo sono disposti in sequenza.</span><span class="sxs-lookup"><span data-stu-id="03785-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="03785-120">Specifica che il layout campo viene fornito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="03785-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="03785-121">Ottiene le informazioni semantiche sul tipo.</span><span class="sxs-lookup"><span data-stu-id="03785-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="03785-122">Specifica che il tipo è una classe.</span><span class="sxs-lookup"><span data-stu-id="03785-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="03785-123">Specifica che il tipo è un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="03785-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="03785-124">Specifica che il tipo è astratto.</span><span class="sxs-lookup"><span data-stu-id="03785-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="03785-125">Specifica che il tipo non può essere estesa.</span><span class="sxs-lookup"><span data-stu-id="03785-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="03785-126">Specifica che il nome della classe è speciale.</span><span class="sxs-lookup"><span data-stu-id="03785-126">Specifies that the class name is special.</span></span> <span data-ttu-id="03785-127">Viene descritto il relativo nome come.</span><span class="sxs-lookup"><span data-stu-id="03785-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="03785-128">Specifica che il tipo è stato importato.</span><span class="sxs-lookup"><span data-stu-id="03785-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="03785-129">Specifica che il tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="03785-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="03785-130">Specifica che questo tipo è un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="03785-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="03785-131">Ottiene informazioni sulla codifica e formattate come stringhe.</span><span class="sxs-lookup"><span data-stu-id="03785-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="03785-132">Specifica che il tipo interpreta LPTSTR come ANSI.</span><span class="sxs-lookup"><span data-stu-id="03785-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="03785-133">Specifica che il tipo interpreta LPTSTR come Unicode.</span><span class="sxs-lookup"><span data-stu-id="03785-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="03785-134">Specifica che il tipo interpreta LPTSTR automaticamente.</span><span class="sxs-lookup"><span data-stu-id="03785-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="03785-135">Specifica che il tipo è una codifica non standard, come specificato da `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="03785-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="03785-136">Utilizzare questa maschera per ottenere le informazioni di codifica non standard per l'interoperabilità nativa.</span><span class="sxs-lookup"><span data-stu-id="03785-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="03785-137">Il significato dei valori di questi due bit non è specificato.</span><span class="sxs-lookup"><span data-stu-id="03785-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="03785-138">Specifica che il tipo deve essere inizializzato prima al primo tentativo di accedere a un campo statico.</span><span class="sxs-lookup"><span data-stu-id="03785-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="03785-139">Specifica che il tipo è esportato e un server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="03785-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="03785-140">Questo flag e i flag seguenti vengono utilizzati internamente da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="03785-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="03785-141">Specifica che common language runtime deve verificare la codifica dei nomi.</span><span class="sxs-lookup"><span data-stu-id="03785-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="03785-142">Specifica che il tipo dispone di protezione associata.</span><span class="sxs-lookup"><span data-stu-id="03785-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03785-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03785-143">Requirements</span></span>  
 <span data-ttu-id="03785-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03785-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03785-145">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="03785-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="03785-146">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03785-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03785-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03785-147">See Also</span></span>  
 [<span data-ttu-id="03785-148">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="03785-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
