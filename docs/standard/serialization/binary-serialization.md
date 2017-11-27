---
title: Serializzazione binaria
ms.date: 08/11/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: "5"
author: ViktorHofer
ms.author: mairaw
ms.openlocfilehash: 74ee4e21934c1e4f3fd008664b1315429dc47b37
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="binary-serialization"></a><span data-ttu-id="891dc-102">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="891dc-102">Binary serialization</span></span>

<span data-ttu-id="891dc-103">La serializzazione può essere definita come il processo di archiviazione dello stato di un oggetto su un supporto di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="891dc-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="891dc-104">Durante tale processo, i campi pubblici e privati dell'oggetto e il nome della classe, incluso l'assembly contenente la classe, vengono convertiti in un flusso di byte che viene scritto in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="891dc-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="891dc-105">Quando l'oggetto viene successivamente deserializzato, viene creato un clone esatto dell'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="891dc-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="891dc-106">Quando si implementa un meccanismo di serializzazione in un ambiente orientato agli oggetti, è necessario fare una serie di compromessi tra semplicità di utilizzo e flessibilità.</span><span class="sxs-lookup"><span data-stu-id="891dc-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="891dc-107">Il processo può essere automatizzato in un ambito di grandi dimensioni, purché si disponga di controllo sufficiente sul processo.</span><span class="sxs-lookup"><span data-stu-id="891dc-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="891dc-108">Ad esempio, possono verificarsi situazioni in cui non è sufficiente la semplice serializzazione binaria o potrebbe esserci una ragione specifica per decidere quali campi in una classe devono essere serializzati.</span><span class="sxs-lookup"><span data-stu-id="891dc-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="891dc-109">Nelle sezioni seguenti viene esaminato l'avanzato meccanismo di serializzazione fornito con .NET e vengono evidenziate alcune importanti funzionalità che consentono di personalizzare il processo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="891dc-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="891dc-110">Lo stato di un oggetto codificato UTF-7 o UTF-8 non viene mantenuto se le relative operazioni di serializzazione e deserializzazione vengono eseguite con versioni di .NET Framework diverse.</span><span class="sxs-lookup"><span data-stu-id="891dc-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="891dc-111">Poiché la natura della serializzazione binaria consente la modifica di membri privati all'interno di un oggetto e quindi la modifica dello stato dell'oggetto, sono consigliati altri framework di serializzazione, come JSON.NET, che intervengono sulla superficie dell'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="891dc-111">As the nature of binary serialization allows the modification of private members inside an object and therefore changing the state of it, other serialization frameworks like JSON.NET which operate on the public API surface are recommended.</span></span>

## <a name="binary-serialization-in-net-core"></a><span data-ttu-id="891dc-112">Serializzazione binaria in .NET Core</span><span class="sxs-lookup"><span data-stu-id="891dc-112">Binary serialization in .NET Core</span></span>

<span data-ttu-id="891dc-113">.NET Core supporta la serializzazione binaria con un subset di tipi.</span><span class="sxs-lookup"><span data-stu-id="891dc-113">.NET Core supports binary serialization with a subset of types.</span></span> <span data-ttu-id="891dc-114">È possibile consultare l'elenco dei tipi supportati nella sezione [Tipi serializzabili](#serializable-types).</span><span class="sxs-lookup"><span data-stu-id="891dc-114">You can see the list of supported types in the [Serializable types section](#serializable-types).</span></span> <span data-ttu-id="891dc-115">È garantita la serializzazione dei tipi definiti tra .NET Framework 4.5.1 e versioni successive e tra .NET Core 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="891dc-115">The defined set of types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="891dc-116">Altre implementazioni di .NET, ad esempio Mono, non sono ufficialmente supportate ma dovrebbero comunque funzionare.</span><span class="sxs-lookup"><span data-stu-id="891dc-116">Other .NET implementations, such as Mono, aren't officially supported but should also be working.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="891dc-117">Tipi serializzabili</span><span class="sxs-lookup"><span data-stu-id="891dc-117">Serializable types</span></span>

- <xref:System.AggregateException?displayProperty=nameWithType>   
- <xref:System.Array?displayProperty=nameWithType>   
- <xref:System.ArraySegment%601?displayProperty=nameWithType>   
- <xref:System.Attribute?displayProperty=nameWithType>   
- <xref:System.Boolean?displayProperty=nameWithType>   
- <xref:System.Byte?displayProperty=nameWithType>   
- <xref:System.Char?displayProperty=nameWithType>   
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>   
- <xref:System.Collections.BitArray?displayProperty=nameWithType>   
- <xref:System.Collections.Comparer?displayProperty=nameWithType>   
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>   
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>   
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>   
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>   
- <xref:System.Collections.Queue?displayProperty=nameWithType>   
- <xref:System.Collections.SortedList?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>   
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>   
- <xref:System.Collections.Stack?displayProperty=nameWithType>   
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>   
- <span data-ttu-id="891dc-118"><xref:System.DBNull?displayProperty=nameWithType>(disponibile in .NET Core 2.0.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="891dc-118"><xref:System.DBNull?displayProperty=nameWithType> (available in .NET Core 2.0.2 and later versions)</span></span>   
- <xref:System.Data.DataSet?displayProperty=nameWithType>   
- <xref:System.Data.DataTable?displayProperty=nameWithType>   
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>   
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>   
- <xref:System.DateTime?displayProperty=nameWithType>   
- <xref:System.DateTimeOffset?displayProperty=nameWithType>   
- <xref:System.Decimal?displayProperty=nameWithType>   
- <xref:System.Double?displayProperty=nameWithType>   
- <xref:System.Drawing.Color?displayProperty=nameWithType>   
- <xref:System.Drawing.Point?displayProperty=nameWithType>   
- <xref:System.Drawing.PointF?displayProperty=nameWithType>   
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>   
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>   
- <xref:System.Drawing.Size?displayProperty=nameWithType>   
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>   
- <xref:System.Enum?displayProperty=nameWithType>   
- <xref:System.Exception?displayProperty=nameWithType>   
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>   
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>   
- <xref:System.Guid?displayProperty=nameWithType>   
- <xref:System.Int16?displayProperty=nameWithType>   
- <xref:System.Int32?displayProperty=nameWithType>   
- <xref:System.Int64?displayProperty=nameWithType>   
- <xref:System.IntPtr?displayProperty=nameWithType>   
- <xref:System.Net.Cookie?displayProperty=nameWithType>   
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>   
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>   
- <xref:System.Nullable%601?displayProperty=nameWithType>   
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>   
- <xref:System.Numerics.Complex?displayProperty=nameWithType>   
- <xref:System.Object?displayProperty=nameWithType>   
- <xref:System.SByte?displayProperty=nameWithType>   
- <xref:System.Single?displayProperty=nameWithType>   
- <xref:System.String?displayProperty=nameWithType>   
- <xref:System.StringComparer?displayProperty=nameWithType>   
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>   
- <xref:System.TimeSpan?displayProperty=nameWithType>   
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>   
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>   
- <xref:System.Tuple?displayProperty=nameWithType>   
- <xref:System.UInt16?displayProperty=nameWithType>   
- <xref:System.UInt32?displayProperty=nameWithType>   
- <xref:System.UInt64?displayProperty=nameWithType>   
- <xref:System.UIntPtr?displayProperty=nameWithType>   
- <xref:System.Uri?displayProperty=nameWithType>   
- <span data-ttu-id="891dc-119"><xref:System.ValueTuple?displayProperty=nameWithType>(non serializzabile in .NET Framework 4.7 e versioni precedenti)</span><span class="sxs-lookup"><span data-stu-id="891dc-119"><xref:System.ValueTuple?displayProperty=nameWithType> (not serializable in .NET Framework 4.7 and earlier versions)</span></span>  
- <xref:System.ValueType?displayProperty=nameWithType>   
- <xref:System.Version?displayProperty=nameWithType>   
- <xref:System.WeakReference?displayProperty=nameWithType>   
- <xref:System.WeakReference%601?displayProperty=nameWithType>   

## <a name="in-this-section"></a><span data-ttu-id="891dc-120">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="891dc-120">In this section</span></span>

 [<span data-ttu-id="891dc-121">Concetti relativi alla serializzazione</span><span class="sxs-lookup"><span data-stu-id="891dc-121">Serialization Concepts</span></span>](../../../docs/standard/serialization/serialization-concepts.md)  
 <span data-ttu-id="891dc-122">Vengono illustrati due scenari in cui la serializzazione risulta utile: quando si conservano i dati da archiviare e quando si trasferiscono oggetti tra più domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="891dc-122">Discusses two scenarios where serialization is useful: when persisting data to storage and when passing objects across application domains.</span></span>  
  
 [<span data-ttu-id="891dc-123">Serializzazione di base</span><span class="sxs-lookup"><span data-stu-id="891dc-123">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 <span data-ttu-id="891dc-124">Descrive come utilizzare i formattatori binari e SOAP per serializzare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="891dc-124">Describes how to use the binary and SOAP formatters to serialize objects.</span></span>  
  
 [<span data-ttu-id="891dc-125">Serializzazione selettiva</span><span class="sxs-lookup"><span data-stu-id="891dc-125">Selective Serialization</span></span>](../../../docs/standard/serialization/selective-serialization.md)  
 <span data-ttu-id="891dc-126">Descrive come impedire la serializzazione di alcuni membri di una classe.</span><span class="sxs-lookup"><span data-stu-id="891dc-126">Describes how to prevent some members of a class from being serialized.</span></span>  
  
 [<span data-ttu-id="891dc-127">Serializzazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="891dc-127">Custom Serialization</span></span>](../../../docs/standard/serialization/custom-serialization.md)  
 <span data-ttu-id="891dc-128">Descrive come personalizzare la serializzazione per una classe usando l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="891dc-128">Describes how to customize serialization for a class by using the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 [<span data-ttu-id="891dc-129">Passaggi del processo di serializzazione</span><span class="sxs-lookup"><span data-stu-id="891dc-129">Steps in the Serialization Process</span></span>](../../../docs/standard/serialization/steps-in-the-serialization-process.md)  
 <span data-ttu-id="891dc-130">Descrive il corso di azioni intraprese dalla serializzazione quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize%2A> su un formattatore.</span><span class="sxs-lookup"><span data-stu-id="891dc-130">Describes the course of action serialization takes when the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a formatter.</span></span>  
  
 [<span data-ttu-id="891dc-131">Serializzazione a tolleranza di versione</span><span class="sxs-lookup"><span data-stu-id="891dc-131">Version Tolerant Serialization</span></span>](../../../docs/standard/serialization/version-tolerant-serialization.md)  
 <span data-ttu-id="891dc-132">Spiega come creare tipi serializzabili modificabili nel tempo evitando che le applicazioni generino eccezioni.</span><span class="sxs-lookup"><span data-stu-id="891dc-132">Explains how to create serializable types that can be modified over time without causing applications to throw exceptions.</span></span>  
  
 [<span data-ttu-id="891dc-133">Linee guida relative alla serializzazione</span><span class="sxs-lookup"><span data-stu-id="891dc-133">Serialization Guidelines</span></span>](../../../docs/standard/serialization/serialization-guidelines.md)  
 <span data-ttu-id="891dc-134">Fornisce alcune linee guida generali che consentono di decidere quando serializzare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="891dc-134">Provides some general guidelines for deciding when to serialize an object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="891dc-135">Riferimento</span><span class="sxs-lookup"><span data-stu-id="891dc-135">Reference</span></span>  
 <xref:System.Runtime.Serialization>  
 <span data-ttu-id="891dc-136">Contiene classi utilizzabili per la serializzazione e la deserializzazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="891dc-136">Contains classes that can be used for serializing and deserializing objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="891dc-137">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="891dc-137">Related sections</span></span>  
 [<span data-ttu-id="891dc-138">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="891dc-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 <span data-ttu-id="891dc-139">Descrive il meccanismo della serializzazione XML incluso nel Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="891dc-139">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>  
  
 [<span data-ttu-id="891dc-140">Sicurezza e serializzazione</span><span class="sxs-lookup"><span data-stu-id="891dc-140">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)  
 <span data-ttu-id="891dc-141">Descrive le linee guida per la creazione di codice protetto da seguire in caso di scrittura di codice che esegue la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="891dc-141">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>  
  
 [<span data-ttu-id="891dc-142">Oggetti remoti</span><span class="sxs-lookup"><span data-stu-id="891dc-142">Remote Objects</span></span>](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)  
 <span data-ttu-id="891dc-143">Vengono descritti i diversi metodi di comunicazione disponibili in .NET Framework per le comunicazioni remote.</span><span class="sxs-lookup"><span data-stu-id="891dc-143">Describes the various communications methods available in the .NET Framework for remote communications.</span></span>  
  
 [<span data-ttu-id="891dc-144">Servizi Web XML creati mediante ASP.NET e tramite client di servizi Web XML</span><span class="sxs-lookup"><span data-stu-id="891dc-144">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 <span data-ttu-id="891dc-145">Fornisce gli argomenti che descrivono e spiegano come programmare i servizi Web XML creati tramite ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="891dc-145">Provides topics that describe and explain how to program XML Web services created using ASP.NET.</span></span>
