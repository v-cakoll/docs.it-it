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
# <a name="binary-serialization"></a>Serializzazione binaria

La serializzazione può essere definita come il processo di archiviazione dello stato di un oggetto su un supporto di archiviazione. Durante tale processo, i campi pubblici e privati dell'oggetto e il nome della classe, incluso l'assembly contenente la classe, vengono convertiti in un flusso di byte che viene scritto in un flusso di dati. Quando l'oggetto viene successivamente deserializzato, viene creato un clone esatto dell'oggetto originale.

Quando si implementa un meccanismo di serializzazione in un ambiente orientato agli oggetti, è necessario fare una serie di compromessi tra semplicità di utilizzo e flessibilità. Il processo può essere automatizzato in un ambito di grandi dimensioni, purché si disponga di controllo sufficiente sul processo. Ad esempio, possono verificarsi situazioni in cui non è sufficiente la semplice serializzazione binaria o potrebbe esserci una ragione specifica per decidere quali campi in una classe devono essere serializzati. Nelle sezioni seguenti viene esaminato l'avanzato meccanismo di serializzazione fornito con .NET e vengono evidenziate alcune importanti funzionalità che consentono di personalizzare il processo in base alle esigenze.

> [!NOTE]
> Lo stato di un oggetto codificato UTF-7 o UTF-8 non viene mantenuto se le relative operazioni di serializzazione e deserializzazione vengono eseguite con versioni di .NET Framework diverse.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Poiché la natura della serializzazione binaria consente la modifica di membri privati all'interno di un oggetto e quindi la modifica dello stato dell'oggetto, sono consigliati altri framework di serializzazione, come JSON.NET, che intervengono sulla superficie dell'API pubblica.

## <a name="binary-serialization-in-net-core"></a>Serializzazione binaria in .NET Core

.NET Core supporta la serializzazione binaria con un subset di tipi. È possibile consultare l'elenco dei tipi supportati nella sezione [Tipi serializzabili](#serializable-types). È garantita la serializzazione dei tipi definiti tra .NET Framework 4.5.1 e versioni successive e tra .NET Core 2.0 e versioni successive. Altre implementazioni di .NET, ad esempio Mono, non sono ufficialmente supportate ma dovrebbero comunque funzionare.

### <a name="serializable-types"></a>Tipi serializzabili

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
- <xref:System.DBNull?displayProperty=nameWithType>(disponibile in .NET Core 2.0.2 e versioni successive)   
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
- <xref:System.ValueTuple?displayProperty=nameWithType>(non serializzabile in .NET Framework 4.7 e versioni precedenti)  
- <xref:System.ValueType?displayProperty=nameWithType>   
- <xref:System.Version?displayProperty=nameWithType>   
- <xref:System.WeakReference?displayProperty=nameWithType>   
- <xref:System.WeakReference%601?displayProperty=nameWithType>   

## <a name="in-this-section"></a>In questa sezione

 [Concetti relativi alla serializzazione](../../../docs/standard/serialization/serialization-concepts.md)  
 Vengono illustrati due scenari in cui la serializzazione risulta utile: quando si conservano i dati da archiviare e quando si trasferiscono oggetti tra più domini dell'applicazione.  
  
 [Serializzazione di base](../../../docs/standard/serialization/basic-serialization.md)  
 Descrive come utilizzare i formattatori binari e SOAP per serializzare gli oggetti.  
  
 [Serializzazione selettiva](../../../docs/standard/serialization/selective-serialization.md)  
 Descrive come impedire la serializzazione di alcuni membri di una classe.  
  
 [Serializzazione personalizzata](../../../docs/standard/serialization/custom-serialization.md)  
 Descrive come personalizzare la serializzazione per una classe usando l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.  
  
 [Passaggi del processo di serializzazione](../../../docs/standard/serialization/steps-in-the-serialization-process.md)  
 Descrive il corso di azioni intraprese dalla serializzazione quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize%2A> su un formattatore.  
  
 [Serializzazione a tolleranza di versione](../../../docs/standard/serialization/version-tolerant-serialization.md)  
 Spiega come creare tipi serializzabili modificabili nel tempo evitando che le applicazioni generino eccezioni.  
  
 [Linee guida relative alla serializzazione](../../../docs/standard/serialization/serialization-guidelines.md)  
 Fornisce alcune linee guida generali che consentono di decidere quando serializzare un oggetto.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Runtime.Serialization>  
 Contiene classi utilizzabili per la serializzazione e la deserializzazione di oggetti.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 Descrive il meccanismo della serializzazione XML incluso nel Common Language Runtime.  
  
 [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md)  
 Descrive le linee guida per la creazione di codice protetto da seguire in caso di scrittura di codice che esegue la serializzazione.  
  
 [Oggetti remoti](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58)  
 Vengono descritti i diversi metodi di comunicazione disponibili in .NET Framework per le comunicazioni remote.  
  
 [Servizi Web XML creati mediante ASP.NET e tramite client di servizi Web XML](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 Fornisce gli argomenti che descrivono e spiegano come programmare i servizi Web XML creati tramite ASP.NET.
