---
title: Serializzazione binaria
description: Questo articolo descrive la serializzazione binaria e i tipi per i quali .NET Core lo supporta. Tenere presente i pericoli della serializzazione binaria e delle alternative.
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 4ed76437b743da842d6ba07d29fe7985f824abf0
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421280"
---
# <a name="binary-serialization"></a><span data-ttu-id="45974-104">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="45974-104">Binary serialization</span></span>

<span data-ttu-id="45974-105">La serializzazione può essere definita come il processo di archiviazione dello stato di un oggetto su un supporto di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="45974-105">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="45974-106">Durante tale processo, i campi pubblici e privati dell'oggetto e il nome della classe, incluso l'assembly contenente la classe, vengono convertiti in un flusso di byte che viene scritto in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="45974-106">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="45974-107">Quando l'oggetto viene successivamente deserializzato, viene creato un clone esatto dell'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="45974-107">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="45974-108">Quando si implementa un meccanismo di serializzazione in un ambiente orientato agli oggetti, è necessario fare una serie di compromessi tra semplicità di utilizzo e flessibilità.</span><span class="sxs-lookup"><span data-stu-id="45974-108">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="45974-109">Il processo può essere automatizzato in un ambito di grandi dimensioni, purché si disponga di controllo sufficiente sul processo.</span><span class="sxs-lookup"><span data-stu-id="45974-109">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="45974-110">Ad esempio, possono verificarsi situazioni in cui non è sufficiente la semplice serializzazione binaria o potrebbe esserci una ragione specifica per decidere quali campi in una classe devono essere serializzati.</span><span class="sxs-lookup"><span data-stu-id="45974-110">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="45974-111">Nelle sezioni seguenti viene esaminato l'avanzato meccanismo di serializzazione fornito con .NET e vengono evidenziate alcune importanti funzionalità che consentono di personalizzare il processo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="45974-111">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="45974-112">Lo stato di un oggetto codificato UTF-7 o UTF-8 non viene mantenuto se le relative operazioni di serializzazione e deserializzazione vengono eseguite con versioni di .NET Framework diverse.</span><span class="sxs-lookup"><span data-stu-id="45974-112">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="45974-113">Con la serializzazione binaria è possibile modificare membri privati all'interno di un oggetto e quindi modificarne lo stato.</span><span class="sxs-lookup"><span data-stu-id="45974-113">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="45974-114">Per questo motivo, sono consigliati altri Framework di serializzazione, <xref:System.Text.Json?displayProperty=fullName> ad esempio, che operano sulla superficie dell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="45974-114">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="45974-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="45974-115">.NET Core</span></span>

<span data-ttu-id="45974-116">.NET Core supporta la serializzazione binaria per un subset di tipi.</span><span class="sxs-lookup"><span data-stu-id="45974-116">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="45974-117">È possibile visualizzare l'elenco dei tipi supportati nella sezione [tipi serializzabili](#serializable-types) riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="45974-117">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="45974-118">I tipi elencati sono sicuramente serializzabili tra .NET Framework 4.5.1 e versioni successive e tra .NET Core 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="45974-118">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="45974-119">Altre implementazioni di .NET, ad esempio mono, non sono ufficialmente supportate, ma dovrebbero anche funzionare.</span><span class="sxs-lookup"><span data-stu-id="45974-119">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="45974-120">Tipi serializzabili</span><span class="sxs-lookup"><span data-stu-id="45974-120">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="45974-121">Type</span><span class="sxs-lookup"><span data-stu-id="45974-121">Type</span></span> | <span data-ttu-id="45974-122">Note</span><span class="sxs-lookup"><span data-stu-id="45974-122">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="45974-123">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="45974-124">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="45974-125">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="45974-126">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="45974-127">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="45974-128">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="45974-129">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="45974-130">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="45974-131">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="45974-132">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="45974-133">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="45974-134">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="45974-135">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-136">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="45974-137">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="45974-138">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="45974-139">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="45974-140">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-140">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="45974-141">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-141">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="45974-142">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-142">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="45974-143">La serializzazione da .NET Framework a .NET Core non è supportata.</span><span class="sxs-lookup"><span data-stu-id="45974-143">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="45974-144">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="45974-145">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="45974-146">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="45974-147">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="45974-148">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="45974-149">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-150">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="45974-151">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-151">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="45974-152">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="45974-153">A partire da .NET Core 2.0.2 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="45974-153">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="45974-154">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="45974-155">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="45974-156">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-156">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="45974-157">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="45974-158">Se si imposta `RemotingFormat` su `SerializationFormat.Binary` , può essere scambiato solo con .net core 2,1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="45974-158">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="45974-159">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="45974-160">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="45974-161">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="45974-162">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="45974-163">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="45974-164">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="45974-165">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="45974-166">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="45974-167">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="45974-168">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="45974-169">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-169">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="45974-170">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-170">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="45974-171">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-171">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="45974-172">La serializzazione da .NET Framework a .NET Core non è supportata</span><span class="sxs-lookup"><span data-stu-id="45974-172">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="45974-173">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="45974-174">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="45974-175">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="45974-176">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="45974-177">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="45974-178">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="45974-179">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-180">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="45974-181">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="45974-182">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="45974-183">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-184">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="45974-185">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="45974-186">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="45974-187">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="45974-188">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="45974-189">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-190">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="45974-191">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="45974-192">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-193">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-194">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="45974-195">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="45974-196">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-197">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="45974-198">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="45974-199">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="45974-200">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-201">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="45974-202">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-203">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="45974-204">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-205">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="45974-206">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-206">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-207">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="45974-208">A partire da .NET Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="45974-208">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="45974-209">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="45974-210">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="45974-211">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-212">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="45974-213">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-214">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="45974-215">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="45974-216">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="45974-217">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-218">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="45974-219">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="45974-220">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="45974-221">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="45974-222">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="45974-223">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="45974-224">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="45974-225">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="45974-226">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="45974-227">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-228">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="45974-229">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="45974-230">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="45974-231">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="45974-232">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="45974-233">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="45974-234">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="45974-235">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="45974-236">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="45974-237">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="45974-238">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="45974-239">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="45974-240">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="45974-241">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="45974-242">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="45974-243">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="45974-244">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="45974-245">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="45974-246">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="45974-247">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="45974-248">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="45974-249">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="45974-250">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="45974-251">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="45974-252">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="45974-253">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="45974-254">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="45974-255">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="45974-256">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="45974-257">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="45974-258">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="45974-259">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-259">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="45974-260">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-260">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="45974-261">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-261">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="45974-262">La serializzazione da .NET Framework a .NET Core non è supportata.</span><span class="sxs-lookup"><span data-stu-id="45974-262">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="45974-263">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="45974-264">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="45974-265">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="45974-266">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="45974-267">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="45974-268">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="45974-269">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="45974-270">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="45974-271">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="45974-272">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="45974-273">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="45974-274">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="45974-275">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="45974-276">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="45974-277">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="45974-278">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="45974-279">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="45974-280">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="45974-281">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-281">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="45974-282">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="45974-283">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-283">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="45974-284">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="45974-285">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="45974-286">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-286">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="45974-287">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-287">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="45974-288">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-288">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="45974-289">Dati di serializzazione limitati.</span><span class="sxs-lookup"><span data-stu-id="45974-289">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="45974-290">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="45974-291">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="45974-292">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="45974-293">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="45974-294">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="45974-295">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="45974-296">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="45974-297">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="45974-298">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="45974-299">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="45974-300">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="45974-301">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="45974-302">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="45974-303">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="45974-304">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="45974-305">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="45974-306">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="45974-307">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="45974-308">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="45974-309">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="45974-310">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="45974-311">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="45974-312">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="45974-313">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="45974-314">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="45974-315">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="45974-316">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="45974-317">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="45974-318">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="45974-319">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="45974-320">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="45974-321">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-321">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="45974-322">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="45974-323">Non serializzabile in .NET Framework 4,7 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="45974-323">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="45974-324">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="45974-325">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="45974-326">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="45974-327">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="45974-328">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-328">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="45974-329">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-329">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="45974-330">A partire da .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="45974-330">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="45974-331">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45974-331">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="45974-332">Contiene classi utilizzabili per la serializzazione e la deserializzazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="45974-332">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="45974-333">[Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="45974-333">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="45974-334">Descrive il meccanismo della serializzazione XML incluso nel Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="45974-334">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="45974-335">[Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="45974-335">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="45974-336">Descrive le linee guida per la creazione di codice protetto da seguire in caso di scrittura di codice che esegue la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="45974-336">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="45974-337">[Servizi remoti .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45974-337">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="45974-338">Vengono descritti i vari metodi a partire da .NET Framework per le comunicazioni remote.</span><span class="sxs-lookup"><span data-stu-id="45974-338">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="45974-339">[Servizi Web XML creati con ASP.NET e client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45974-339">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="45974-340">Articoli che descrivono e spiegano come programmare i servizi Web XML creati con ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="45974-340">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
