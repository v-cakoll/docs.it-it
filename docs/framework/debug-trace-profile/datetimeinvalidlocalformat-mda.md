---
title: dateTimeInvalidLocalFormat (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
ms.openlocfilehash: 2fdace8a9c7bcc090fd801be3bd717e4a2b34a87
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217542"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="4114d-102">dateTimeInvalidLocalFormat (MDA)</span><span class="sxs-lookup"><span data-stu-id="4114d-102">dateTimeInvalidLocalFormat MDA</span></span>
<span data-ttu-id="4114d-103">L'assistente al debug gestito `dateTimeInvalidLocalFormat` viene attivato quando per la formattazione di un'istanza di <xref:System.DateTime> archiviata in formato UTC (Universal Coordinated Time) viene usato un formato riservato alle istanze locali di <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="4114d-103">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="4114d-104">Questo assistente non viene attivato per le istanze di <xref:System.DateTime> non specificate o predefinite.</span><span class="sxs-lookup"><span data-stu-id="4114d-104">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="4114d-105">Sintomo</span><span class="sxs-lookup"><span data-stu-id="4114d-105">Symptom</span></span>  
 <span data-ttu-id="4114d-106">Un'applicazione sta serializzando manualmente un'istanza di <xref:System.DateTime> in formato UTC usando un formato locale:</span><span class="sxs-lookup"><span data-stu-id="4114d-106">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="4114d-107">Causa</span><span class="sxs-lookup"><span data-stu-id="4114d-107">Cause</span></span>  
 <span data-ttu-id="4114d-108">Il formato 'z' del metodo <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> include l'offset del fuso orario locale, ad esempio "+10:00" per l'ora di Sydney.</span><span class="sxs-lookup"><span data-stu-id="4114d-108">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="4114d-109">Di conseguenza, verrà generato un risultato significativo solo se il valore di <xref:System.DateTime> è locale.</span><span class="sxs-lookup"><span data-stu-id="4114d-109">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="4114d-110">Se il valore è in formato UTC, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> include l'offset del fuso orario locale, ma non visualizza né modifica l'identificatore del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="4114d-110">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="4114d-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="4114d-111">Resolution</span></span>  
 <span data-ttu-id="4114d-112">Le istanze di <xref:System.DateTime> in formato UTC devono essere formattate in modo che vengano identificate come UTC.</span><span class="sxs-lookup"><span data-stu-id="4114d-112">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="4114d-113">Per indicare un'ora in formato UTC è consigliabile usare una 'Z':</span><span class="sxs-lookup"><span data-stu-id="4114d-113">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="4114d-114">Esiste anche un formato "o" che serializza un'istanza di <xref:System.DateTime> usando la proprietà <xref:System.DateTime.Kind%2A> che viene serializzata correttamente indipendentemente dal fatto che l'istanza sia in formato locale, UTC o non specificato:</span><span class="sxs-lookup"><span data-stu-id="4114d-114">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4114d-115">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="4114d-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="4114d-116">Questo assistente al debug gestito non ha alcun effetto sul runtime.</span><span class="sxs-lookup"><span data-stu-id="4114d-116">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4114d-117">Output</span><span class="sxs-lookup"><span data-stu-id="4114d-117">Output</span></span>  
 <span data-ttu-id="4114d-118">L'attivazione di questo assistente al debug gestito non genera alcun output specifico. È possibile, tuttavia, usare lo stack di chiamate per determinare la posizione della chiamata <xref:System.DateTime.ToString%2A> che ha attivato l'assistente.</span><span class="sxs-lookup"><span data-stu-id="4114d-118">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4114d-119">Configurazione</span><span class="sxs-lookup"><span data-stu-id="4114d-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="4114d-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="4114d-120">Example</span></span>  
 <span data-ttu-id="4114d-121">Si consideri ad esempio un'applicazione che stia serializzando indirettamente un valore <xref:System.DateTime> UTC tramite la classe <xref:System.Xml.XmlConvert> o <xref:System.Data.DataSet>, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="4114d-121">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="4114d-122">Per impostazione predefinita, <xref:System.Xml.XmlConvert> e <xref:System.Data.DataSet> usano formati locali per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="4114d-122">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="4114d-123">Per serializzare altri tipi di valori <xref:System.DateTime>, ad esempio UTC, sono necessarie opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4114d-123">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="4114d-124">Per questo esempio specifico, passare `XmlDateTimeSerializationMode.RoundtripKind` alla chiamata `ToString` su `XmlConvert`.</span><span class="sxs-lookup"><span data-stu-id="4114d-124">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="4114d-125">In questo modo i dati vengono serializzati come ora UTC.</span><span class="sxs-lookup"><span data-stu-id="4114d-125">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="4114d-126">Se si usa <xref:System.Data.DataSet>, impostare la proprietà <xref:System.Data.DataColumn.DateTimeMode%2A> dell'oggetto <xref:System.Data.DataColumn> su <xref:System.Data.DataSetDateTime.Utc>.</span><span class="sxs-lookup"><span data-stu-id="4114d-126">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4114d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4114d-127">See also</span></span>

- <xref:System.Globalization.DateTimeFormatInfo>
- [<span data-ttu-id="4114d-128">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="4114d-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
