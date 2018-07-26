---
title: 'Tipi di base (F #)'
description: 'Individua i tipi di base fondamentali usati nel linguaggio F #.'
ms.date: 07/09/2018
ms.openlocfilehash: fdb5e95e102fcf721569156c7fb3a32604fff1dd
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937198"
---
# <a name="basic-types"></a><span data-ttu-id="1d8b0-103">Tipi di base</span><span class="sxs-lookup"><span data-stu-id="1d8b0-103">Basic types</span></span>

<span data-ttu-id="1d8b0-104">Questo argomento elenca i tipi di base che sono definiti nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="1d8b0-105">Questi tipi sono il più fondamentale in F #, che costituiscono la base di quasi tutti i programmi F #.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="1d8b0-106">Sono un soprainsieme di tipi primitivi di .NET.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="1d8b0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d8b0-107">Type</span></span>|<span data-ttu-id="1d8b0-108">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="1d8b0-108">.NET type</span></span>|<span data-ttu-id="1d8b0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d8b0-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="1d8b0-110">I valori possibili sono `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="1d8b0-111">Valori compresi tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="1d8b0-112">Valori compresi tra -128 e 127.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="1d8b0-113">Valori compresi tra -32768 e 32767.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="1d8b0-114">Valori compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="1d8b0-115">Valori compresi tra -2.147.483.648 e 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="1d8b0-116">Valori compresi tra 0 e 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="1d8b0-117">Valori compresi tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="1d8b0-118">Valori compresi tra 0 e 18.446.744.073.709.551.615.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="1d8b0-119">Un puntatore nativo come un intero con segno.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="1d8b0-120">Un puntatore nativo come intero senza segno.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="1d8b0-121">Valori di tipo carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="1d8b0-122">Testo Unicode.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="1d8b0-123">Tipo di dati che dispone di almeno 28 cifre significative a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="1d8b0-124">non applicabile</span><span class="sxs-lookup"><span data-stu-id="1d8b0-124">not applicable</span></span>|<span data-ttu-id="1d8b0-125">Indica l'assenza di un valore effettivo.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="1d8b0-126">Il tipo ha un solo valore formale, indicato `()`.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="1d8b0-127">Il valore dell'unità, `()`, viene spesso usato come segnaposto in cui è necessario un valore ma nessun valore reale è disponibile o ha senso.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="1d8b0-128">Non indica nessun tipo o valore.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="1d8b0-129">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="1d8b0-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="1d8b0-130">Tipo a virgola mobile a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="1d8b0-131">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="1d8b0-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="1d8b0-132">Un tipo a virgola mobile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-132">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="1d8b0-133">È possibile eseguire calcoli con numeri interi troppo grande per il tipo integer a 64 bit utilizzando il [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="1d8b0-134">`bigint` non è considerato un tipo di base. è un'abbreviazione per `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="1d8b0-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d8b0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d8b0-135">See also</span></span>
[<span data-ttu-id="1d8b0-136">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1d8b0-136">F# Language Reference</span></span>](index.md)
