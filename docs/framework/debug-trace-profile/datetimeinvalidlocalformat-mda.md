---
title: dateTimeInvalidLocalFormat (MDA)
description: Esaminare l'assistente al debug gestito dateTimeInvalidLocalFormat, che viene attivato quando un valore DateTime archiviato dall'ora UTC ottiene un formato DateTime solo locale.
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
ms.openlocfilehash: d092b93af55d2cdf14e9284d8cffcdc8440cbf81
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415992"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="e5290-103">dateTimeInvalidLocalFormat (MDA)</span><span class="sxs-lookup"><span data-stu-id="e5290-103">dateTimeInvalidLocalFormat MDA</span></span>
<span data-ttu-id="e5290-104">L'assistente al debug gestito `dateTimeInvalidLocalFormat` viene attivato quando per la formattazione di un'istanza di <xref:System.DateTime> archiviata in formato UTC (Universal Coordinated Time) viene usato un formato riservato alle istanze locali di <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="e5290-104">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="e5290-105">Questo assistente non viene attivato per le istanze di <xref:System.DateTime> non specificate o predefinite.</span><span class="sxs-lookup"><span data-stu-id="e5290-105">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="e5290-106">Sintomo</span><span class="sxs-lookup"><span data-stu-id="e5290-106">Symptom</span></span>  
 <span data-ttu-id="e5290-107">Un'applicazione sta serializzando manualmente un'istanza di <xref:System.DateTime> in formato UTC usando un formato locale:</span><span class="sxs-lookup"><span data-stu-id="e5290-107">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="e5290-108">Causa</span><span class="sxs-lookup"><span data-stu-id="e5290-108">Cause</span></span>  
 <span data-ttu-id="e5290-109">Il formato 'z' del metodo <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> include l'offset del fuso orario locale, ad esempio "+10:00" per l'ora di Sydney.</span><span class="sxs-lookup"><span data-stu-id="e5290-109">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="e5290-110">Di conseguenza, verrà generato un risultato significativo solo se il valore di <xref:System.DateTime> è locale.</span><span class="sxs-lookup"><span data-stu-id="e5290-110">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="e5290-111">Se il valore è in formato UTC, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> include l'offset del fuso orario locale, ma non visualizza né modifica l'identificatore del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="e5290-111">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="e5290-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="e5290-112">Resolution</span></span>  
 <span data-ttu-id="e5290-113">Le istanze di <xref:System.DateTime> in formato UTC devono essere formattate in modo che vengano identificate come UTC.</span><span class="sxs-lookup"><span data-stu-id="e5290-113">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="e5290-114">Per indicare un'ora in formato UTC è consigliabile usare una 'Z':</span><span class="sxs-lookup"><span data-stu-id="e5290-114">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="e5290-115">Esiste anche un formato "o" che serializza un'istanza di <xref:System.DateTime> usando la proprietà <xref:System.DateTime.Kind%2A> che viene serializzata correttamente indipendentemente dal fatto che l'istanza sia in formato locale, UTC o non specificato:</span><span class="sxs-lookup"><span data-stu-id="e5290-115">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e5290-116">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e5290-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="e5290-117">Questo assistente al debug gestito non ha alcun effetto sul runtime.</span><span class="sxs-lookup"><span data-stu-id="e5290-117">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e5290-118">Output</span><span class="sxs-lookup"><span data-stu-id="e5290-118">Output</span></span>  
 <span data-ttu-id="e5290-119">L'attivazione di questo assistente al debug gestito non genera alcun output specifico. È possibile, tuttavia, usare lo stack di chiamate per determinare la posizione della chiamata <xref:System.DateTime.ToString%2A> che ha attivato l'assistente.</span><span class="sxs-lookup"><span data-stu-id="e5290-119">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e5290-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e5290-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="e5290-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5290-121">Example</span></span>  
 <span data-ttu-id="e5290-122">Si consideri ad esempio un'applicazione che stia serializzando indirettamente un valore <xref:System.DateTime> UTC tramite la classe <xref:System.Xml.XmlConvert> o <xref:System.Data.DataSet>, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="e5290-122">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="e5290-123">Per impostazione predefinita, <xref:System.Xml.XmlConvert> e <xref:System.Data.DataSet> usano formati locali per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="e5290-123">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="e5290-124">Per serializzare altri tipi di valori <xref:System.DateTime>, ad esempio UTC, sono necessarie opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e5290-124">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="e5290-125">Per questo esempio specifico, passare `XmlDateTimeSerializationMode.RoundtripKind` alla chiamata `ToString` su `XmlConvert`.</span><span class="sxs-lookup"><span data-stu-id="e5290-125">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="e5290-126">In questo modo i dati vengono serializzati come ora UTC.</span><span class="sxs-lookup"><span data-stu-id="e5290-126">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="e5290-127">Se si usa <xref:System.Data.DataSet>, impostare la proprietà <xref:System.Data.DataColumn.DateTimeMode%2A> dell'oggetto <xref:System.Data.DataColumn> su <xref:System.Data.DataSetDateTime.Utc>.</span><span class="sxs-lookup"><span data-stu-id="e5290-127">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5290-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e5290-128">See also</span></span>

- <xref:System.Globalization.DateTimeFormatInfo>
- [<span data-ttu-id="e5290-129">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="e5290-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
