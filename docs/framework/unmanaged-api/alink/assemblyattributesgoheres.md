---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
ms.openlocfilehash: 128268bab77c8be5dc809eaa6d2548fc34f13cbd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446615"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="91057-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="91057-102">AssemblyAttributesGoHereS</span></span>

<span data-ttu-id="91057-103">Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="91057-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="91057-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91057-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a><span data-ttu-id="91057-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="91057-105">Remarks</span></span>

<span data-ttu-id="91057-106">I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="91057-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="91057-107">Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="91057-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="91057-108">Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="91057-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="91057-109">I riferimenti a questo tipo indicano gli attributi personalizzati che sono correlati alla sicurezza e non sono multiuso.</span><span class="sxs-lookup"><span data-stu-id="91057-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>

<span data-ttu-id="91057-110">Questi tipi sono contrassegnati come "Internal" all'interno del .NET Framework e si trovano nello spazio dei nomi <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="91057-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="91057-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91057-111">Requirements</span></span>

<span data-ttu-id="91057-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="91057-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="91057-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91057-113">See also</span></span>

- [<span data-ttu-id="91057-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="91057-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="91057-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="91057-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="91057-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="91057-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
