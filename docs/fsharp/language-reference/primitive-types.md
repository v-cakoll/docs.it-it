---
title: Tipi primitivi (F#)
description: 'Individuare i tipi primitivi fondamentali utilizzati nel linguaggio F #.'
ms.date: 05/16/2016
ms.openlocfilehash: efe419e5ebf2e49be9433bbd3025ff290d648296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564469"
---
# <a name="primitive-types"></a><span data-ttu-id="b5011-103">Tipi primitivi</span><span class="sxs-lookup"><span data-stu-id="b5011-103">Primitive Types</span></span>

<span data-ttu-id="b5011-104">Questo argomento elenca i tipi primitivi fondamentali utilizzati nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="b5011-104">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="b5011-105">Specifica anche i tipi .NET corrispondenti e i valori minimi e massimi per ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="b5011-105">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="b5011-106">Riepilogo dei tipi primitivi</span><span class="sxs-lookup"><span data-stu-id="b5011-106">Summary of Primitive Types</span></span>
<span data-ttu-id="b5011-107">Nella tabella seguente sono riepilogate le proprietà dei tipi primitivi F #.</span><span class="sxs-lookup"><span data-stu-id="b5011-107">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="b5011-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="b5011-108">Type</span></span>|<span data-ttu-id="b5011-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="b5011-109">.NET type</span></span>|<span data-ttu-id="b5011-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5011-110">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="b5011-111">I valori possibili sono `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="b5011-111">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="b5011-112">Valori compresi tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="b5011-112">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="b5011-113">Valori compresi tra -128 a 127.</span><span class="sxs-lookup"><span data-stu-id="b5011-113">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="b5011-114">Valori compresi tra -32768 e 32767.</span><span class="sxs-lookup"><span data-stu-id="b5011-114">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="b5011-115">Valori compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="b5011-115">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="b5011-116">Valori compresi tra -2.147.483.648 e 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="b5011-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="b5011-117">Valori compresi tra 0 e 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="b5011-117">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="b5011-118">Valori compresi tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="b5011-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="b5011-119">Valori da 0 a 18.446.744.073.709.551.615.</span><span class="sxs-lookup"><span data-stu-id="b5011-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="b5011-120">Un puntatore nativo come un intero con segno.</span><span class="sxs-lookup"><span data-stu-id="b5011-120">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="b5011-121">Un puntatore nativo come un intero senza segno.</span><span class="sxs-lookup"><span data-stu-id="b5011-121">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="b5011-122">Valori di tipo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="b5011-122">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="b5011-123">Testo Unicode.</span><span class="sxs-lookup"><span data-stu-id="b5011-123">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="b5011-124">Tipo di dati che ha almeno 28 cifre significative a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="b5011-124">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="b5011-125">non applicabile</span><span class="sxs-lookup"><span data-stu-id="b5011-125">not applicable</span></span>|<span data-ttu-id="b5011-126">Indica l'assenza di un valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="b5011-126">Indicates the absence of an actual value.</span></span> <span data-ttu-id="b5011-127">Il tipo ha un solo valore formale, indicato `()`.</span><span class="sxs-lookup"><span data-stu-id="b5011-127">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="b5011-128">Il valore dell'unità, `()`, viene spesso utilizzato come segnaposto in cui è necessario un valore ma nessun valore reale è disponibile o ha senso.</span><span class="sxs-lookup"><span data-stu-id="b5011-128">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="b5011-129">Non indica nessun tipo o valore.</span><span class="sxs-lookup"><span data-stu-id="b5011-129">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="b5011-130">Tipo a virgola mobile a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b5011-130">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="b5011-131">Tipo a virgola mobile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="b5011-131">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="b5011-132">È possibile eseguire calcoli con numeri interi troppo grande per il tipo integer a 64 bit utilizzando il [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo.</span><span class="sxs-lookup"><span data-stu-id="b5011-132">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="b5011-133">`bigint` non viene considerato un tipo primitivo. è un'abbreviazione per `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="b5011-133">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5011-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5011-134">See Also</span></span>
[<span data-ttu-id="b5011-135">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="b5011-135">F# Language Reference</span></span>](index.md)
