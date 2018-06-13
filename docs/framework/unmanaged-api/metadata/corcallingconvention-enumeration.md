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
ms.openlocfilehash: 468ad1acf55c4d1b4fc2b53730f16ee8630cf19b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444015"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="5ece9-102">Enumerazione CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="5ece9-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="5ece9-103">Contiene valori che descrivono i tipi di convenzioni di chiamata eseguite in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5ece9-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ece9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ece9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5ece9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5ece9-105">Members</span></span>  
  
|<span data-ttu-id="5ece9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5ece9-106">Member</span></span>|<span data-ttu-id="5ece9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ece9-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="5ece9-108">Indica una convenzione di chiamata predefinita.</span><span class="sxs-lookup"><span data-stu-id="5ece9-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="5ece9-109">Indica che il metodo accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="5ece9-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="5ece9-110">Indica che la chiamata è per un campo.</span><span class="sxs-lookup"><span data-stu-id="5ece9-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="5ece9-111">Indica che la chiamata è per un metodo locale.</span><span class="sxs-lookup"><span data-stu-id="5ece9-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="5ece9-112">Indica che la chiamata è per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="5ece9-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="5ece9-113">Indica che la chiamata non gestita.</span><span class="sxs-lookup"><span data-stu-id="5ece9-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="5ece9-114">Indica un'istanza di metodo generico.</span><span class="sxs-lookup"><span data-stu-id="5ece9-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="5ece9-115">Indica una chiamata di PInvoke a 64 bit a un metodo che accetta un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="5ece9-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="5ece9-116">Viene descritto un valore a 4 bit non valido.</span><span class="sxs-lookup"><span data-stu-id="5ece9-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="5ece9-117">Indica che la convenzione di chiamata è descritta da ultimi quattro bit.</span><span class="sxs-lookup"><span data-stu-id="5ece9-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="5ece9-118">Indica che il primo bit descrive un `this` parametro.</span><span class="sxs-lookup"><span data-stu-id="5ece9-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="5ece9-119">Indica che un `this` è descritto in modo esplicito nella firma del parametro.</span><span class="sxs-lookup"><span data-stu-id="5ece9-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="5ece9-120">Indica una firma di metodo generico con un numero di argomenti di tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="5ece9-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="5ece9-121">Questo precede un numero di parametri comuni.</span><span class="sxs-lookup"><span data-stu-id="5ece9-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ece9-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5ece9-122">Requirements</span></span>  
 <span data-ttu-id="5ece9-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ece9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ece9-124">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="5ece9-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5ece9-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ece9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ece9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ece9-126">See Also</span></span>  
 [<span data-ttu-id="5ece9-127">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="5ece9-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
