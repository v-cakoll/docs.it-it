---
title: CorElementType Enumeration1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorElementType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorElementType
helpviewer_keywords: CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00f4aa4e87c0deb4b1326cb8bf4256a9307b3393
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="23959-102">CorElementType Enumeration1</span><span class="sxs-lookup"><span data-stu-id="23959-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="23959-103">Specifica un common language runtime <xref:System.Type>, un modificatore di tipo o informazioni su un tipo in una firma del tipo di metadati.</span><span class="sxs-lookup"><span data-stu-id="23959-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23959-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23959-104">Syntax</span></span>  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a><span data-ttu-id="23959-105">Membri</span><span class="sxs-lookup"><span data-stu-id="23959-105">Members</span></span>  
  
|<span data-ttu-id="23959-106">Membro</span><span class="sxs-lookup"><span data-stu-id="23959-106">Member</span></span>|<span data-ttu-id="23959-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23959-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="23959-108">Utilizzata internamente.</span><span class="sxs-lookup"><span data-stu-id="23959-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="23959-109">Un tipo void.</span><span class="sxs-lookup"><span data-stu-id="23959-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="23959-110">Un tipo booleano</span><span class="sxs-lookup"><span data-stu-id="23959-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="23959-111">Tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="23959-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="23959-112">Intero con segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="23959-113">Intero senza segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="23959-114">Intero con segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="23959-115">Intero senza segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="23959-116">Intero con segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="23959-117">Intero senza segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="23959-118">Intero con segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="23959-119">Intero senza segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="23959-120">Virgola mobile a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="23959-121">Un punto a virgola mobile a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="23959-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="23959-122">Un tipo System. String.</span><span class="sxs-lookup"><span data-stu-id="23959-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="23959-123">Un modificatore di tipo puntatore.</span><span class="sxs-lookup"><span data-stu-id="23959-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="23959-124">Un modificatore di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="23959-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="23959-125">Un modificatore di tipo valore.</span><span class="sxs-lookup"><span data-stu-id="23959-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="23959-126">Un modificatore di tipo classe.</span><span class="sxs-lookup"><span data-stu-id="23959-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="23959-127">Un modificatore di tipo della variabile di classe.</span><span class="sxs-lookup"><span data-stu-id="23959-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="23959-128">Un modificatore di tipo matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="23959-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="23959-129">Un modificatore di tipo per i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="23959-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="23959-130">Riferimento tipizzato.</span><span class="sxs-lookup"><span data-stu-id="23959-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="23959-131">Dimensioni di un numero intero nativo.</span><span class="sxs-lookup"><span data-stu-id="23959-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="23959-132">Dimensione dell'intero senza segno nativo.</span><span class="sxs-lookup"><span data-stu-id="23959-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="23959-133">Un puntatore a una funzione.</span><span class="sxs-lookup"><span data-stu-id="23959-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="23959-134">Un tipo System. Object.</span><span class="sxs-lookup"><span data-stu-id="23959-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="23959-135">Unidimensionale, zero modificatore di tipo matrice con limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="23959-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="23959-136">Un modificatore di tipo della variabile di metodo.</span><span class="sxs-lookup"><span data-stu-id="23959-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="23959-137">Modificatore richiesto da un linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="23959-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="23959-138">Un modificatore facoltativo del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="23959-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="23959-139">Utilizzata internamente.</span><span class="sxs-lookup"><span data-stu-id="23959-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="23959-140">Tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="23959-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="23959-141">Utilizzata internamente.</span><span class="sxs-lookup"><span data-stu-id="23959-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="23959-142">Un modificatore di tipo è sentinel per un elenco di un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="23959-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="23959-143">Utilizzata internamente.</span><span class="sxs-lookup"><span data-stu-id="23959-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23959-144">Note</span><span class="sxs-lookup"><span data-stu-id="23959-144">Remarks</span></span>  
 <span data-ttu-id="23959-145">I modificatori di tipo costituiscono la base per la rappresentazione di tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="23959-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="23959-146">Oggetto `CorElementType` valore del modificatore del tipo viene applicato a quello che segue immediatamente nella firma del tipo.</span><span class="sxs-lookup"><span data-stu-id="23959-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="23959-147">Il valore che segue il `CorElementType` valore del modificatore del tipo può essere un `CorElementType` valore di tipo semplice, un token di metadati o altri valori, come specificato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="23959-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23959-148">Tutti i numeri (*numero*, *argomento Count*, *token di metadati*, *rank*, *conteggio*e *associato*) vengono archiviati come numeri interi compressi.</span><span class="sxs-lookup"><span data-stu-id="23959-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="23959-149">Vedere [Standard ECMA-335: Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) nel sito Web di ECMA per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="23959-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="23959-150">Modificatore di tipo</span><span class="sxs-lookup"><span data-stu-id="23959-150">Type modifier</span></span>|<span data-ttu-id="23959-151">Formato</span><span class="sxs-lookup"><span data-stu-id="23959-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="23959-152">ELEMENT_TYPE_PTR < un `CorElementType` valore ></span><span class="sxs-lookup"><span data-stu-id="23959-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="23959-153">ELEMENT_TYPE_BYREF < un `CorElementType` valore ></span><span class="sxs-lookup"><span data-stu-id="23959-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="23959-154">ELEMENT_TYPE_VALUETYPE < un `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="23959-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="23959-155">ELEMENT_TYPE_CLASS < un `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="23959-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="23959-156">ELEMENT_TYPE_VAR \<numero ></span><span class="sxs-lookup"><span data-stu-id="23959-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="23959-157">ELEMENT_TYPE_ARRAY < un `CorElementType` valore > \<rank > \<count1 > \<bound1 >... \<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="23959-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="23959-158">ELEMENT_TYPE_GENERICINST < un `mdTypeDef` token di metadati > \<argomento Count > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="23959-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="23959-159">ELEMENT_TYPE_FNPTR \<firma completa per la funzione, inclusi la convenzione di chiamata ></span><span class="sxs-lookup"><span data-stu-id="23959-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="23959-160">ELEMENT_TYPE_SZARRAY < un `CorElementType` valore ></span><span class="sxs-lookup"><span data-stu-id="23959-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="23959-161">ELEMENT_TYPE_MVAR \<numero ></span><span class="sxs-lookup"><span data-stu-id="23959-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="23959-162">ELEMENT_TYPE _ < un `mdTypeRef` o `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="23959-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="23959-163">E_T_CMOD_OPT < un `mdTypeRef` o `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="23959-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23959-164">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23959-164">Requirements</span></span>  
 <span data-ttu-id="23959-165">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23959-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23959-166">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="23959-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="23959-167">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23959-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23959-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23959-168">See Also</span></span>  
 [<span data-ttu-id="23959-169">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="23959-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
