---
title: tipi copiabili e non copiabili
description: Informazioni sui tipi copiabili e non copiabili. I tipi di dati copiabili in genere sono rappresentati nella memoria gestita e non gestita e non richiedono una gestione speciale.
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 68f4197a2710b6825c83bbc51daaf8f6b5a2c81f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621535"
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="b0dd7-104">tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="b0dd7-104">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="b0dd7-105">La maggior parte dei tipi di dati ha una rappresentazione comune sia nella memoria gestita sia in quella non gestita e non richiede quindi una gestione particolare tramite il gestore di marshalling di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-105">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="b0dd7-106">Questi tipi sono definiti *copiabili da BLT*, poiché non richiedono la conversione quando vengono passati tra codice gestito e codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-106">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="b0dd7-107">Le strutture restituite dalle chiamate platform invoke devono essere tipi copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-107">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="b0dd7-108">Platform invoke non supporta strutture non copiabili da BLT come tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-108">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="b0dd7-109">I tipi dello spazio dei nomi <xref:System> elencati di seguito sono copiabili da BLT:</span><span class="sxs-lookup"><span data-stu-id="b0dd7-109">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="b0dd7-110">Sono copiabili da BLT anche i tipi complessi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0dd7-110">The following complex types are also blittable types:</span></span>  
  
- <span data-ttu-id="b0dd7-111">Matrici unidimensionali di tipi copiabili da BLT, come una matrice di integer.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-111">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="b0dd7-112">Non è tuttavia copiabile da BLT un tipo contenente una matrice variabile di tipi copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-112">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
- <span data-ttu-id="b0dd7-113">Tipi di valore formattati contenenti solo tipi copiabili da BLT (e classi, se sottoposti a marshalling come tipi formattati).</span><span class="sxs-lookup"><span data-stu-id="b0dd7-113">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="b0dd7-114">Per altre informazioni sui tipi di valore formattati, vedere [marshalling predefinito per i tipi di valore](default-marshaling-behavior.md#default-marshaling-for-value-types).</span><span class="sxs-lookup"><span data-stu-id="b0dd7-114">For more information about formatted value types, see [Default marshaling for value types](default-marshaling-behavior.md#default-marshaling-for-value-types).</span></span>  
  
 <span data-ttu-id="b0dd7-115">Non sono copiabili da BLT i riferimenti a oggetti,</span><span class="sxs-lookup"><span data-stu-id="b0dd7-115">Object references are not blittable.</span></span> <span data-ttu-id="b0dd7-116">incluse le matrici di riferimenti a oggetti che invece sono copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-116">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="b0dd7-117">È possibile, ad esempio, definire una struttura copiabile da BLT, ma non un tipo copiabile da BLT contenente una matrice di riferimenti alla struttura.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-117">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="b0dd7-118">Per motivi di ottimizzazione, le matrici di tipi e classi copiabili da BLT contenenti solo membri copiabili da BLT vengono [bloccate](copying-and-pinning.md) e non copiate durante il marshalling.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-118">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="b0dd7-119">Quando il chiamante e il chiamato si trovano nello stesso apartment, può sembrare che il marshalling di questi tipi venga eseguito come parametri In/Out.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-119">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="b0dd7-120">Il marshalling di questi tipi, in realtà, viene eseguito come parametri In ed è necessario applicare gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> se si vuole eseguire il marshalling dell'argomento come parametro In/Out.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-120">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="b0dd7-121">Alcuni tipi di dati gestiti richiedono una rappresentazione diversa in un ambiente non gestito.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-121">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="b0dd7-122">Questi tipi di dati non copiabili da BLT devono essere convertiti in un formato di cui è possibile eseguire il marshalling.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-122">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="b0dd7-123">Le stringhe gestite, ad esempio, sono tipi non copiabili da BLT perché devono essere convertite in oggetti stringa prima di poter eseguire il marshalling.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-123">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="b0dd7-124">Nella tabella seguente sono elencati i tipi non copiabili da BLT dello spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-124">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="b0dd7-125">Anche i [delegati](default-marshaling-behavior.md#default-marshaling-for-delegates), ossia le strutture di dati che fanno riferimento a un metodo statico o a un'istanza di classe, non sono copiabili da BLT.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-125">[Delegates](default-marshaling-behavior.md#default-marshaling-for-delegates), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="b0dd7-126">Tipi non copiabili da BLT</span><span class="sxs-lookup"><span data-stu-id="b0dd7-126">Non-blittable type</span></span>|<span data-ttu-id="b0dd7-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0dd7-127">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="b0dd7-128">System.Array</span><span class="sxs-lookup"><span data-stu-id="b0dd7-128">System.Array</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="b0dd7-129">Viene convertito in una matrice di tipo C o in `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-129">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="b0dd7-130">[System. Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b0dd7-130">[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))</span></span>|<span data-ttu-id="b0dd7-131">Viene convertito in un valore a 1, 2 o 4 byte con `true` pari a 1 o -1.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-131">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="b0dd7-132">[System. Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b0dd7-132">[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))</span></span>|<span data-ttu-id="b0dd7-133">Viene convertito in un carattere Unicode o ANSI.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-133">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="b0dd7-134">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b0dd7-134">[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))</span></span>|<span data-ttu-id="b0dd7-135">Viene convertito in un'interfaccia di classe.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-135">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="b0dd7-136">System. Object</span><span class="sxs-lookup"><span data-stu-id="b0dd7-136">System.Object</span></span>](default-marshaling-for-objects.md)|<span data-ttu-id="b0dd7-137">Viene convertito in una variante o in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-137">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="b0dd7-138">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="b0dd7-138">System.Mdarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="b0dd7-139">Viene convertito in una matrice di tipo C o in `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-139">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="b0dd7-140">System. String</span><span class="sxs-lookup"><span data-stu-id="b0dd7-140">System.String</span></span>](default-marshaling-for-strings.md)|<span data-ttu-id="b0dd7-141">Viene convertito in una stringa che termina con un riferimento Null o un BSTR.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-141">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="b0dd7-142">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b0dd7-142">[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))</span></span>|<span data-ttu-id="b0dd7-143">Viene convertito in una struttura con un layout a memoria fissa.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-143">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="b0dd7-144">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="b0dd7-144">System.Szarray</span></span>](default-marshaling-for-arrays.md)|<span data-ttu-id="b0dd7-145">Viene convertito in una matrice di tipo C o in `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-145">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="b0dd7-146">I tipi di classe e oggetto sono supportati solo dall'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="b0dd7-146">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="b0dd7-147">Per i tipi corrispondenti in Visual Basic, C#, e C++, vedere [Panoramica della libreria di classi](../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b0dd7-147">For corresponding types in Visual Basic, C#, and C++, see the [Class Library Overview](../../standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0dd7-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0dd7-148">See also</span></span>

- [<span data-ttu-id="b0dd7-149">comportamento predefinito del marshalling</span><span class="sxs-lookup"><span data-stu-id="b0dd7-149">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
