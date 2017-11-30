---
title: Note sull'implementazione del supporto per il tipo XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26b071f3-1261-47ef-8690-0717f5cd93c1
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5e99573fc3a82db7798426172a13a78e10c65636
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-type-support-implementation-notes"></a><span data-ttu-id="e769d-102">Note sull'implementazione del supporto per il tipo XML</span><span class="sxs-lookup"><span data-stu-id="e769d-102">XML Type Support Implementation Notes</span></span>
<span data-ttu-id="e769d-103">In questo argomento vengono descritti alcuni dettagli sull'implementazione di cui è consigliabile essere a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="e769d-103">This topic describes some implementation details that you want to be aware of.</span></span>  
  
## <a name="list-mappings"></a><span data-ttu-id="e769d-104">Mapping degli elenchi</span><span class="sxs-lookup"><span data-stu-id="e769d-104">List Mappings</span></span>  
 <span data-ttu-id="e769d-105">Il <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type []**, e <xref:System.String> tipi vengono utilizzati per rappresentare tipi di elenco di XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="e769d-105">The <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type[]**, and <xref:System.String> types are used to represent XML Schema definition language (XSD) list types.</span></span>  
  
## <a name="union-mappings"></a><span data-ttu-id="e769d-106">Mapping delle unioni</span><span class="sxs-lookup"><span data-stu-id="e769d-106">Union Mappings</span></span>  
 <span data-ttu-id="e769d-107">I tipi di unione vengono rappresentati usando il tipo <xref:System.Xml.Schema.XmlAtomicValue> o <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e769d-107">Union types are represented using the <xref:System.Xml.Schema.XmlAtomicValue> or <xref:System.String> type.</span></span> <span data-ttu-id="e769d-108">Pertanto, il tipo di origine o il tipo di destinazione devono sempre essere <xref:System.String> o <xref:System.Xml.Schema.XmlAtomicValue>.</span><span class="sxs-lookup"><span data-stu-id="e769d-108">The source type or the destination type must therefore always be either <xref:System.String> or <xref:System.Xml.Schema.XmlAtomicValue>.</span></span>  
  
 <span data-ttu-id="e769d-109">Se l'oggetto <xref:System.Xml.Schema.XmlSchemaDatatype> rappresenta un tipo di elenco, tale oggetto converte il valore della stringa di input in un elenco di uno o più oggetti.</span><span class="sxs-lookup"><span data-stu-id="e769d-109">If the <xref:System.Xml.Schema.XmlSchemaDatatype> object represents a list type the object converts the input string value to a list of one or more objects.</span></span> <span data-ttu-id="e769d-110">Se l'oggetto <xref:System.Xml.Schema.XmlSchemaDatatype> rappresenta un tipo di unione, viene eseguito un tentativo di analisi del valore di input come tipo membro dell'unione.</span><span class="sxs-lookup"><span data-stu-id="e769d-110">If the <xref:System.Xml.Schema.XmlSchemaDatatype> represents a union type then an attempt is made to parse the input value as a member type of the union.</span></span> <span data-ttu-id="e769d-111">Se il tentativo di analisi non viene eseguito correttamente, viene tentata la conversione con il successivo membro dell'unione e così via fino a quando la conversione non viene eseguita correttamente o non sono disponibili altri tipi di membro con cui provare. In questo caso verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e769d-111">If the parse attempt fails then the conversion is attempted with the next member of the union and so on until the conversion is successful, or there are no other member types to try, in which case an exception is thrown.</span></span>  
  
## <a name="differences-between-clr-and-xml-data-types"></a><span data-ttu-id="e769d-112">Differenze tra i tipi di dati CLR e XML</span><span class="sxs-lookup"><span data-stu-id="e769d-112">Differences Between CLR and XML Data Types</span></span>  
 <span data-ttu-id="e769d-113">Di seguito vengono descritte alcune corrispondenze errate che si possono verificare tra i tipi di dati CLR e i tipi di dati XML e la loro eventuale gestione.</span><span class="sxs-lookup"><span data-stu-id="e769d-113">The following describes certain mismatches that can occur between CLR types and XML data types and how they are handled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e769d-114">Il prefisso `xs` è associato all'indirizzo http://www.w3.org/2001/XMLSchema e all'URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e769d-114">The `xs` prefix is mapped to the http://www.w3.org/2001/XMLSchema and namespace URI.</span></span>  
  
### <a name="systemtimespan-and-xsduration"></a><span data-ttu-id="e769d-115">System.TimeSpan e xs:duration</span><span class="sxs-lookup"><span data-stu-id="e769d-115">System.TimeSpan and xs:duration</span></span>  
 <span data-ttu-id="e769d-116">Il tipo `xs:duration` è parzialmente ordinato, poiché alcuni valori di durata sono diversi ma equivalenti.</span><span class="sxs-lookup"><span data-stu-id="e769d-116">The `xs:duration` type is partially ordered in that there are certain duration values that are different but equivalent.</span></span> <span data-ttu-id="e769d-117">Ciò significa che per il tipo `xs:duration` il valore di 1 mese (P1M) è minore di 32 giorni (P32D), maggiore di 27 giorni (P27D) ed equivalente a 28, 29 o 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="e769d-117">This means that for the `xs:duration` type value such as 1 month (P1M) is less than 32 days (P32D), larger than 27 days (P27D) and equivalent to 28, 29 or 30 days.</span></span>  
  
 <span data-ttu-id="e769d-118">La classe <xref:System.TimeSpan> non supporta questo ordinamento parziale.</span><span class="sxs-lookup"><span data-stu-id="e769d-118">The <xref:System.TimeSpan> class does not support this partial ordering.</span></span> <span data-ttu-id="e769d-119">Invece, stabilisce un numero specifico di giorni per 1 anno e 1 mese: rispettivamente 365 e 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="e769d-119">Instead, it picks a specific number of days for 1 year and 1 month; 365 days and 30 days respectively.</span></span>  
  
 <span data-ttu-id="e769d-120">Per altre informazioni sul tipo `xs:duration`, vedere la raccomandazione W3C XML Schema Part 2: Datatypes all'indirizzo http://www.w3.org/TR/xmlschema-2/ (informazioni in lingua inglese).</span><span class="sxs-lookup"><span data-stu-id="e769d-120">For more information on the `xs:duration` type, see the W3C XML Schema Part 2: Datatypes Recommendation at http://www.w3.org/TR/xmlschema-2/.</span></span>  
  
### <a name="xstime-gregorian-date-types-and-systemdatetime"></a><span data-ttu-id="e769d-121">xs:time, tipi di date gregoriane e System.DateTime</span><span class="sxs-lookup"><span data-stu-id="e769d-121">xs:time, Gregorian Date Types, and System.DateTime</span></span>  
 <span data-ttu-id="e769d-122">Quando un valore `xs:time` è associato a un oggetto <xref:System.DateTime>, il campo <xref:System.DateTime.MinValue> viene usato per inizializzare le proprietà relative alla data dell'oggetto <xref:System.DateTime> (ad esempio, <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> e <xref:System.DateTime.Day%2A>) impostandole sul valore <xref:System.DateTime> più basso possibile.</span><span class="sxs-lookup"><span data-stu-id="e769d-122">When an `xs:time` value is mapped to a <xref:System.DateTime> object, the <xref:System.DateTime.MinValue> field is used to initialize the date properties of the <xref:System.DateTime> object (such as <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, and <xref:System.DateTime.Day%2A>) to the smallest possible <xref:System.DateTime> value.</span></span>  
  
 <span data-ttu-id="e769d-123">Allo stesso modo, anche istanze di `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` e `xs:gMonthDay` vengono associate a un oggetto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="e769d-123">Similarly, instances of `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` and `xs:gMonthDay` are also mapped to a <xref:System.DateTime> object.</span></span> <span data-ttu-id="e769d-124">Le proprietà inutilizzate nell'oggetto <xref:System.DateTime> vengono inizializzate impostandole su quelle da <xref:System.DateTime.MinValue>.</span><span class="sxs-lookup"><span data-stu-id="e769d-124">Unused properties on the <xref:System.DateTime> object are initialized to those from <xref:System.DateTime.MinValue>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e769d-125">Non è possibile usare il valore <xref:System.DateTime.Year%2A?displayProperty=nameWithType> quando il contenuto è tipizzato come `xs:gMonthDay`.</span><span class="sxs-lookup"><span data-stu-id="e769d-125">You cannot rely on the <xref:System.DateTime.Year%2A?displayProperty=nameWithType> value when the content is typed as `xs:gMonthDay`.</span></span> <span data-ttu-id="e769d-126">In questo caso il valore <xref:System.DateTime.Year%2A?displayProperty=nameWithType> è sempre impostato su 1904.</span><span class="sxs-lookup"><span data-stu-id="e769d-126">The <xref:System.DateTime.Year%2A?displayProperty=nameWithType> value is always set to 1904 in this case.</span></span>  
  
### <a name="xsanyuri-and-systemuri"></a><span data-ttu-id="e769d-127">xs:anyURI e System.Uri</span><span class="sxs-lookup"><span data-stu-id="e769d-127">xs:anyURI and System.Uri</span></span>  
 <span data-ttu-id="e769d-128">Quando un'istanza di `xs:anyURI` che rappresenta un URI relativo viene associata a un tipo <xref:System.Uri>, l'oggetto <xref:System.Uri> non dispone di un URI di base.</span><span class="sxs-lookup"><span data-stu-id="e769d-128">When an instance of `xs:anyURI` that represents a relative URI is mapped to a <xref:System.Uri>, the <xref:System.Uri> object does not have a base URI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e769d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e769d-129">See Also</span></span>  
 [<span data-ttu-id="e769d-130">Supporto di tipi di dati nelle classi System.Xml</span><span class="sxs-lookup"><span data-stu-id="e769d-130">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
