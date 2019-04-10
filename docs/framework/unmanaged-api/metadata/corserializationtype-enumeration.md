---
title: Enumerazione CorSerializationType
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15b1f6be2dac6bc7566852791ac22e495949521c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179627"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="f44ed-102">Enumerazione CorSerializationType</span><span class="sxs-lookup"><span data-stu-id="f44ed-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="f44ed-103">Specifica come un oggetto viene serializzato da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="f44ed-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f44ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f44ed-104">Syntax</span></span>  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="f44ed-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f44ed-105">Members</span></span>  
  
|<span data-ttu-id="f44ed-106">Member</span><span class="sxs-lookup"><span data-stu-id="f44ed-106">Member</span></span>|<span data-ttu-id="f44ed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f44ed-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="f44ed-108">Serializzazione dell'oggetto non è definita.</span><span class="sxs-lookup"><span data-stu-id="f44ed-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="f44ed-109">L'oggetto viene serializzato come un tipo Boolean</span><span class="sxs-lookup"><span data-stu-id="f44ed-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="f44ed-110">Oggetto viene serializzato come tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="f44ed-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="f44ed-111">Oggetto viene serializzato come un intero con segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="f44ed-112">Oggetto viene serializzato come un intero senza segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="f44ed-113">Oggetto viene serializzato come un intero con segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="f44ed-114">Oggetto viene serializzato come un intero senza segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="f44ed-115">Oggetto viene serializzato come un intero con segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="f44ed-116">Oggetto viene serializzato come un intero senza segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="f44ed-117">Oggetto viene serializzato come un intero con segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="f44ed-118">Oggetto viene serializzato come un intero senza segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="f44ed-119">Oggetto viene serializzato come virgola mobile a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="f44ed-120">Oggetto viene serializzato come un punto a virgola mobile a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="f44ed-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="f44ed-121">Oggetto viene serializzato come tipo System. String.</span><span class="sxs-lookup"><span data-stu-id="f44ed-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="f44ed-122">L'oggetto viene serializzato come un singolo-dimensionale, matrice di limite inferiore zero.</span><span class="sxs-lookup"><span data-stu-id="f44ed-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="f44ed-123">Oggetto viene serializzato come tipo generico.</span><span class="sxs-lookup"><span data-stu-id="f44ed-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="f44ed-124">Oggetto viene serializzato come oggetto con tag.</span><span class="sxs-lookup"><span data-stu-id="f44ed-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="f44ed-125">Oggetto viene serializzato come un campo.</span><span class="sxs-lookup"><span data-stu-id="f44ed-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="f44ed-126">Oggetto viene serializzato come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="f44ed-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="f44ed-127">Oggetto viene serializzato come enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f44ed-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f44ed-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f44ed-128">Requirements</span></span>  
 <span data-ttu-id="f44ed-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f44ed-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f44ed-130">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="f44ed-130">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="f44ed-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f44ed-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f44ed-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f44ed-132">See also</span></span>

- [<span data-ttu-id="f44ed-133">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f44ed-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
