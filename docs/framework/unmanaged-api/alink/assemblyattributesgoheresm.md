---
title: Classe AssemblyAttributesGoHereSM (CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b156ed9c318e71a408ea10f2744911a85faedc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790338"
---
# <a name="assemblyattributesgoheresm-class"></a><span data-ttu-id="45818-102">Classe AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="45818-102">AssemblyAttributesGoHereSM Class</span></span>

<span data-ttu-id="45818-103">Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="45818-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="45818-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45818-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a><span data-ttu-id="45818-105">Note</span><span class="sxs-lookup"><span data-stu-id="45818-105">Remarks</span></span>

<span data-ttu-id="45818-106">I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="45818-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="45818-107">Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="45818-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="45818-108">Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="45818-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="45818-109">I riferimenti a questo tipo indicano gli attributi personalizzati che sono correlati alla sicurezza e sono multiuso.</span><span class="sxs-lookup"><span data-stu-id="45818-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>

<span data-ttu-id="45818-110">Questi tipi sono contrassegnati come "interni" all'interno di .NET Framework e si trovano nel <xref:System.Runtime.CompilerServices> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="45818-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="45818-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45818-111">Requirements</span></span>

<span data-ttu-id="45818-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="45818-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="45818-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45818-113">See also</span></span>

- [<span data-ttu-id="45818-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="45818-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="45818-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="45818-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="45818-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="45818-116">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
