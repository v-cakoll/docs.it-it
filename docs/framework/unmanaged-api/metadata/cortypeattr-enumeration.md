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
ms.openlocfilehash: b1586184c91619994ba0dfc9d5dcc277c10f99cf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436454"
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="bcd5d-102">Enumerazione CorTypeAttr</span><span class="sxs-lookup"><span data-stu-id="bcd5d-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="bcd5d-103">Contiene valori che indicano i metadati del tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcd5d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="bcd5d-105">Members</span><span class="sxs-lookup"><span data-stu-id="bcd5d-105">Members</span></span>  
  
|<span data-ttu-id="bcd5d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bcd5d-106">Member</span></span>|<span data-ttu-id="bcd5d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcd5d-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="bcd5d-108">Utilizzato per informazioni sulla visibilità del tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="bcd5d-109">Specifica che il tipo non è nell'ambito pubblico.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="bcd5d-110">Specifica che il tipo è nell'ambito pubblico.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="bcd5d-111">Specifica che il tipo è annidato con visibilità pubblica.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="bcd5d-112">Specifica che il tipo è annidato con visibilità privata.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="bcd5d-113">Specifica che il tipo è annidato con visibilità della famiglia.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="bcd5d-114">Specifica che il tipo è annidato con visibilità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="bcd5d-115">Specifica che il tipo è annidato con visibilità della famiglia e dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="bcd5d-116">Specifica che il tipo è annidato con visibilità della famiglia o dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="bcd5d-117">Ottiene le informazioni sul layout per il tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="bcd5d-118">Specifica che i campi di questo tipo vengono disposti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="bcd5d-119">Specifica che i campi di questo tipo sono disposti in sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="bcd5d-120">Specifica che il layout del campo viene fornito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="bcd5d-121">Ottiene le informazioni semantiche sul tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="bcd5d-122">Specifica che il tipo è una classe.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="bcd5d-123">Specifica che il tipo è un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="bcd5d-124">Specifica che il tipo è astratto.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="bcd5d-125">Specifica che il tipo non può essere esteso.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="bcd5d-126">Specifica che il nome della classe è speciale.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-126">Specifies that the class name is special.</span></span> <span data-ttu-id="bcd5d-127">Il nome descrive come.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="bcd5d-128">Specifica che il tipo viene importato.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="bcd5d-129">Specifica che il tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="bcd5d-130">Specifica che questo tipo è un tipo di Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-130">Specifies that this type is a Windows Runtime type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="bcd5d-131">Ottiene informazioni sul modo in cui le stringhe vengono codificate e formattate.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="bcd5d-132">Specifica che questo tipo interpreta un LPTSTR come ANSI.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="bcd5d-133">Specifica che questo tipo interpreta un LPTSTR come Unicode.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="bcd5d-134">Specifica che questo tipo interpreta automaticamente un LPTSTR.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="bcd5d-135">Specifica che il tipo ha una codifica non standard, come specificato da `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="bcd5d-136">Usare questa maschera per ottenere informazioni di codifica non standard per l'interoperabilità nativa.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="bcd5d-137">Il significato dei valori di questi due bit non è specificato.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="bcd5d-138">Specifica che il tipo deve essere inizializzato prima del primo tentativo di accesso a un campo statico.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="bcd5d-139">Specifica che il tipo viene esportato e un server d'avanzamento del tipo.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="bcd5d-140">Questo flag e i flag seguenti vengono usati internamente dal Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="bcd5d-141">Specifica che il Common Language Runtime deve controllare la codifica dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="bcd5d-142">Specifica che il tipo è associato alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bcd5d-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bcd5d-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcd5d-143">Requirements</span></span>  
 <span data-ttu-id="bcd5d-144">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd5d-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd5d-145">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="bcd5d-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bcd5d-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd5d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd5d-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcd5d-147">See also</span></span>

- [<span data-ttu-id="bcd5d-148">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="bcd5d-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
