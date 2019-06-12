---
title: Enumerazione CorTypeAttr
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f65c2f74ec5efda027d90b3ffda9a5da5c239122
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025721"
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="be2d7-102">Enumerazione CorTypeAttr</span><span class="sxs-lookup"><span data-stu-id="be2d7-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="be2d7-103">Contiene valori che indicano i metadati del tipo.</span><span class="sxs-lookup"><span data-stu-id="be2d7-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be2d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be2d7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="be2d7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="be2d7-105">Members</span></span>  
  
|<span data-ttu-id="be2d7-106">Member</span><span class="sxs-lookup"><span data-stu-id="be2d7-106">Member</span></span>|<span data-ttu-id="be2d7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be2d7-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="be2d7-108">Utilizzato per informazioni sul tipo di visibilità.</span><span class="sxs-lookup"><span data-stu-id="be2d7-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="be2d7-109">Specifica che il tipo non è in ambito pubblico.</span><span class="sxs-lookup"><span data-stu-id="be2d7-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="be2d7-110">Specifica che il tipo sia in ambito pubblico.</span><span class="sxs-lookup"><span data-stu-id="be2d7-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="be2d7-111">Specifica che il tipo è annidato e con visibilità pubblica.</span><span class="sxs-lookup"><span data-stu-id="be2d7-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="be2d7-112">Specifica che il tipo è annidato e con visibilità privata.</span><span class="sxs-lookup"><span data-stu-id="be2d7-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="be2d7-113">Specifica che il tipo è annidato e con visibilità della famiglia.</span><span class="sxs-lookup"><span data-stu-id="be2d7-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="be2d7-114">Specifica che il tipo è annidato e con visibilità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="be2d7-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="be2d7-115">Specifica che il tipo è annidato e con visibilità dell'assembly e della famiglia.</span><span class="sxs-lookup"><span data-stu-id="be2d7-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="be2d7-116">Specifica che il tipo è annidato e con visibilità dell'assembly o della famiglia.</span><span class="sxs-lookup"><span data-stu-id="be2d7-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="be2d7-117">Ottiene le informazioni sul layout per il tipo.</span><span class="sxs-lookup"><span data-stu-id="be2d7-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="be2d7-118">Specifica che i campi di questo tipo vengono disposti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="be2d7-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="be2d7-119">Specifica che i campi di questo tipo vengono disposti in ordine sequenziale.</span><span class="sxs-lookup"><span data-stu-id="be2d7-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="be2d7-120">Specifica che il layout campo viene fornito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="be2d7-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="be2d7-121">Ottiene informazioni semantiche sul tipo.</span><span class="sxs-lookup"><span data-stu-id="be2d7-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="be2d7-122">Specifica che il tipo è una classe.</span><span class="sxs-lookup"><span data-stu-id="be2d7-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="be2d7-123">Specifica che il tipo è un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="be2d7-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="be2d7-124">Specifica che il tipo è astratto.</span><span class="sxs-lookup"><span data-stu-id="be2d7-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="be2d7-125">Specifica che il tipo non può essere estesa.</span><span class="sxs-lookup"><span data-stu-id="be2d7-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="be2d7-126">Specifica che il nome della classe è speciale.</span><span class="sxs-lookup"><span data-stu-id="be2d7-126">Specifies that the class name is special.</span></span> <span data-ttu-id="be2d7-127">Viene descritto il relativo nome come.</span><span class="sxs-lookup"><span data-stu-id="be2d7-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="be2d7-128">Specifica che il tipo viene importato.</span><span class="sxs-lookup"><span data-stu-id="be2d7-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="be2d7-129">Specifica che il tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="be2d7-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="be2d7-130">Specifica che questo tipo è un tipo Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="be2d7-130">Specifies that this type is a Windows Runtime type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="be2d7-131">Ottiene informazioni su come le stringhe vengono codificate e formattate.</span><span class="sxs-lookup"><span data-stu-id="be2d7-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="be2d7-132">Specifica che questo tipo interpreta LPTSTR come ANSI.</span><span class="sxs-lookup"><span data-stu-id="be2d7-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="be2d7-133">Specifica che questo tipo interpreta LPTSTR come Unicode.</span><span class="sxs-lookup"><span data-stu-id="be2d7-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="be2d7-134">Specifica che questo tipo interpreta LPTSTR automaticamente.</span><span class="sxs-lookup"><span data-stu-id="be2d7-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="be2d7-135">Specifica che il tipo ha una codifica non standard, come specificato da `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="be2d7-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="be2d7-136">Usare questa maschera per ottenere informazioni di codifica non standard per l'interoperabilità nativa.</span><span class="sxs-lookup"><span data-stu-id="be2d7-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="be2d7-137">Il significato dei valori di questi due bit non è specificato.</span><span class="sxs-lookup"><span data-stu-id="be2d7-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="be2d7-138">Specifica che il tipo deve essere inizializzato prima del primo tentativo di accedere a un campo statico.</span><span class="sxs-lookup"><span data-stu-id="be2d7-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="be2d7-139">Specifica che il tipo viene esportato e un server d'inoltro.</span><span class="sxs-lookup"><span data-stu-id="be2d7-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="be2d7-140">Questo flag e i flag seguenti vengono utilizzati internamente da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="be2d7-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="be2d7-141">Specifica che common language runtime deve verificare la codifica dei nomi.</span><span class="sxs-lookup"><span data-stu-id="be2d7-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="be2d7-142">Specifica che il tipo è associata una sicurezza.</span><span class="sxs-lookup"><span data-stu-id="be2d7-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be2d7-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be2d7-143">Requirements</span></span>  
 <span data-ttu-id="be2d7-144">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be2d7-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be2d7-145">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="be2d7-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="be2d7-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be2d7-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2d7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be2d7-147">See also</span></span>

- [<span data-ttu-id="be2d7-148">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="be2d7-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
