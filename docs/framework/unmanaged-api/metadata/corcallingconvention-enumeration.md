---
title: Enumerazione CorCallingConvention
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c27669c8473bd52d3b82a14d570340ac38d1e07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523246"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="72b03-102">Enumerazione CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="72b03-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="72b03-103">Contiene valori che descrivono i tipi di convenzioni di chiamata eseguite in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="72b03-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72b03-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="72b03-105">Membri</span><span class="sxs-lookup"><span data-stu-id="72b03-105">Members</span></span>  
  
|<span data-ttu-id="72b03-106">Membro</span><span class="sxs-lookup"><span data-stu-id="72b03-106">Member</span></span>|<span data-ttu-id="72b03-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72b03-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="72b03-108">Indica una convenzione di chiamata predefinita.</span><span class="sxs-lookup"><span data-stu-id="72b03-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="72b03-109">Indica che il metodo accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="72b03-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="72b03-110">Indica che la chiamata è per un campo.</span><span class="sxs-lookup"><span data-stu-id="72b03-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="72b03-111">Indica che la chiamata è per un metodo locale.</span><span class="sxs-lookup"><span data-stu-id="72b03-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="72b03-112">Indica che la chiamata è per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="72b03-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="72b03-113">Indica che la chiamata non gestita.</span><span class="sxs-lookup"><span data-stu-id="72b03-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="72b03-114">Indica una creazione di un'istanza di metodo generico.</span><span class="sxs-lookup"><span data-stu-id="72b03-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="72b03-115">Indica una chiamata di PInvoke a 64 bit a un metodo che accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="72b03-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="72b03-116">Descrive un valore a 4 bit non è valido.</span><span class="sxs-lookup"><span data-stu-id="72b03-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="72b03-117">Indica che la convenzione di chiamata è descritto dai bit ultime quattro.</span><span class="sxs-lookup"><span data-stu-id="72b03-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="72b03-118">Indica che il primo bit descrive un `this` parametro.</span><span class="sxs-lookup"><span data-stu-id="72b03-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="72b03-119">Indica che un `this` parametro è descritto in modo esplicito nella firma.</span><span class="sxs-lookup"><span data-stu-id="72b03-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="72b03-120">Indica una firma di metodo generico con un numero di argomenti di tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="72b03-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="72b03-121">Questa configurazione precede un numero di parametri comuni.</span><span class="sxs-lookup"><span data-stu-id="72b03-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72b03-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72b03-122">Requirements</span></span>  
 <span data-ttu-id="72b03-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72b03-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b03-124">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="72b03-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="72b03-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b03-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b03-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72b03-126">See also</span></span>
- [<span data-ttu-id="72b03-127">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="72b03-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
