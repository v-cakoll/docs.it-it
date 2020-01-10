---
title: Gestione di spazi dei nomi in un documento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
ms.openlocfilehash: 64ef9fd4ca3a9a83b9cd3eba9cb952b0f668e9f0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710700"
---
# <a name="managing-namespaces-in-an-xml-document"></a><span data-ttu-id="64d16-102">Gestione di spazi dei nomi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="64d16-102">Managing Namespaces in an XML Document</span></span>
<span data-ttu-id="64d16-103">Tramite gli spazi dei nomi XML è possibile associare i nomi degli attributi e degli elementi di un documento XML a URI personalizzati e predefiniti.</span><span class="sxs-lookup"><span data-stu-id="64d16-103">XML namespaces associate element and attribute names in an XML document with custom and predefined URIs.</span></span> <span data-ttu-id="64d16-104">Per creare queste associazioni, è possibile definire i prefissi per gli URI dello spazio dei nomi e usare i prefissi in questione per qualificare i nomi degli attributi e degli elementi nei dati XML.</span><span class="sxs-lookup"><span data-stu-id="64d16-104">To create these associations, you define prefixes for namespace URIs, and use those prefixes to qualify element and attribute names in XML data.</span></span> <span data-ttu-id="64d16-105">Con gli spazi dei nomi è possibile evitare i conflitti tra i nomi degli elementi e degli attributi e consentire la gestione e la convalida degli elementi e degli attributi con lo stesso nome in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="64d16-105">Namespaces prevent element and attribute name collisions, and enable elements and attributes of the same name to be handled and validated differently.</span></span>  
  
<a name="declare"></a>   
## <a name="declaring-namespaces"></a><span data-ttu-id="64d16-106">Dichiarazione degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-106">Declaring namespaces</span></span>  
 <span data-ttu-id="64d16-107">Per dichiarare uno spazio dei nomi in un elemento, usare l'attributo `xmlns:` riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="64d16-107">To declare a namespace on an element, you use the `xmlns:` attribute:</span></span>  
  
 `xmlns:<name>=<"uri">`  
  
 <span data-ttu-id="64d16-108">dove `<name>` è il prefisso dello spazio dei nomi e `<"uri">` è l'URI tramite cui viene identificato lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="64d16-108">where `<name>` is the namespace prefix and `<"uri">` is the URI that identifies the namespace.</span></span> <span data-ttu-id="64d16-109">Al termine della dichiarazione, il prefisso può essere usato per qualificare elementi e attributi in un documento XML e associarli all'URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="64d16-109">After you declare the prefix, you can use it to qualify elements and attributes in an XML document and associate them with the namespace URI.</span></span> <span data-ttu-id="64d16-110">Poiché viene usato nell'intero documento, il prefisso dello spazio dei nomi deve essere breve.</span><span class="sxs-lookup"><span data-stu-id="64d16-110">Because the namespace prefix is used throughout a document, it should be short in length.</span></span>  
  
 <span data-ttu-id="64d16-111">Nell'esempio vengono definiti due elementi `BOOK`.</span><span class="sxs-lookup"><span data-stu-id="64d16-111">This example defines two `BOOK` elements.</span></span> <span data-ttu-id="64d16-112">Il primo elemento è qualificato dal prefisso `mybook`, mentre il secondo dal prefisso `bb`.</span><span class="sxs-lookup"><span data-stu-id="64d16-112">The first element is qualified by the prefix, `mybook`, and the second element is qualified by the prefix, `bb`.</span></span> <span data-ttu-id="64d16-113">Ogni prefisso è associato a un diverso URI dello spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="64d16-113">Each prefix is associated with a different namespace URI:</span></span>  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines">  
```  
  
 <span data-ttu-id="64d16-114">Per indicare che un elemento fa parte di un determinato spazio dei nomi, aggiungervi il prefisso dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="64d16-114">To signify that an element is a part of a particular namespace, add the namespace prefix to it.</span></span> <span data-ttu-id="64d16-115">Ad esempio, se un elemento `Author` appartiene allo spazio dei nomi `mybook`, viene dichiarato come `<mybook:Author>`.</span><span class="sxs-lookup"><span data-stu-id="64d16-115">For example, if a `Author` element belongs to the `mybook` namespace, it is declared as `<mybook:Author>`.</span></span>  
  
<a name="scope"></a>   
## <a name="declaration-scope"></a><span data-ttu-id="64d16-116">Ambito della dichiarazione</span><span class="sxs-lookup"><span data-stu-id="64d16-116">Declaration scope</span></span>  
 <span data-ttu-id="64d16-117">Uno spazio dei nomi entra in vigore dal punto della dichiarazione fino alla fine dell'elemento in cui è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="64d16-117">A namespace is effective from its point of declaration until the end of the element it was declared in.</span></span> <span data-ttu-id="64d16-118">In questo esempio, lo spazio dei nomi definito nell'elemento `BOOK` non è applicabile agli elementi esterni all'elemento `BOOK`, come l'elemento `Publisher`:</span><span class="sxs-lookup"><span data-stu-id="64d16-118">In this example, the namespace defined in the `BOOK` element doesn't apply to elements outside the `BOOK` element, such as the `Publisher` element:</span></span>  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 <span data-ttu-id="64d16-119">Uno spazio dei nomi deve essere dichiarato prima di poterlo usare, ma non deve trovarsi all'inizio del documento XML.</span><span class="sxs-lookup"><span data-stu-id="64d16-119">A namespace must be declared before it can be used, but it doesn't have to appear at the top of the XML document.</span></span>  
  
 <span data-ttu-id="64d16-120">Quando si usano più spazi dei nomi in un documento XML, è possibile definire uno spazio dei nomi come spazio dei nomi predefinito per creare un documento più chiaro.</span><span class="sxs-lookup"><span data-stu-id="64d16-120">When you use multiple namespaces in an XML document, you can define one namespace as the default namespace to create a cleaner looking document.</span></span> <span data-ttu-id="64d16-121">Lo spazio dei nomi predefinito viene dichiarato nell'elemento radice e si applica a tutti gli elementi non qualificati nel documento.</span><span class="sxs-lookup"><span data-stu-id="64d16-121">The default namespace is declared in the root element and applies to all unqualified elements in the document.</span></span> <span data-ttu-id="64d16-122">Gli spazi dei nomi predefiniti sono applicabili solo agli elementi, non agli attributi.</span><span class="sxs-lookup"><span data-stu-id="64d16-122">Default namespaces apply to elements only, not to attributes.</span></span>  
  
 <span data-ttu-id="64d16-123">Per usare lo spazio dei nomi predefinito, omettere il prefisso e i due punti dalla dichiarazione nell'elemento:</span><span class="sxs-lookup"><span data-stu-id="64d16-123">To use the default namespace, omit the prefix and the colon from the declaration on the element:</span></span>  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
```  
  
## <a name="managing-namespaces"></a><span data-ttu-id="64d16-124">Gestione degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-124">Managing namespaces</span></span>  
 <span data-ttu-id="64d16-125">Tramite la classe <xref:System.Xml.XmlNamespaceManager> viene archiviata una raccolta di URI dello spazio dei nomi e i relativi prefissi consentendo all'utente di cercare, aggiungere e rimuovere spazi dei nomi da questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="64d16-125">The <xref:System.Xml.XmlNamespaceManager> class stores a collection of namespace URIs and their prefixes, and lets you look up, add, and remove namespaces from this collection.</span></span> <span data-ttu-id="64d16-126">In determinati contesti, questa classe viene richiesta per migliorare le prestazioni di elaborazione del codice XML.</span><span class="sxs-lookup"><span data-stu-id="64d16-126">In certain contexts, this class is required for better XML processing performance.</span></span> <span data-ttu-id="64d16-127">Ad esempio, la classe <xref:System.Xml.Xsl.XsltContext> usa <xref:System.Xml.XmlNamespaceManager> per fornire il supporto XPath.</span><span class="sxs-lookup"><span data-stu-id="64d16-127">For example, the <xref:System.Xml.Xsl.XsltContext> class uses <xref:System.Xml.XmlNamespaceManager> for XPath support.</span></span>  
  
 <span data-ttu-id="64d16-128">Il gestore dello spazio dei nomi non esegue convalide sugli spazi dei nomi, ma si presuppone che i prefissi e gli spazi dei nomi siano già stati verificati e siano conformi alla specifica [W3C Namespaces](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="64d16-128">The namespace manager doesn't perform any validation on the namespaces, but assumes that prefixes and namespaces have already been verified and conform to the [W3C Namespaces](https://www.w3.org/TR/REC-xml-names/) specification.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64d16-129">LINQ to XML in [C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) non usano <xref:System.Xml.XmlNamespaceManager> per gestire gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="64d16-129">LINQ TO XML in [C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) don't use <xref:System.Xml.XmlNamespaceManager> to manage namespaces.</span></span> <span data-ttu-id="64d16-130">Per informazioni sulla gestione di spazi dei nomi quando si usa LINQ to XML, vedere [Uso degli spazi dei nomi XML (C#)](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) e [Uso degli spazi dei nomi XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md) nella documentazione di LINQ.</span><span class="sxs-lookup"><span data-stu-id="64d16-130">See [Working with XML Namespaces (C#)](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) and [Working with XML Namespaces (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md) in the LINQ documentation for information about managing namespaces when using LINQ to XML.</span></span>  
  
 <span data-ttu-id="64d16-131">Di seguito sono riportate alcune attività di gestione e ricerca eseguibili con la classe <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="64d16-131">Here are some of the management and lookup tasks you can perform with the <xref:System.Xml.XmlNamespaceManager> class.</span></span> <span data-ttu-id="64d16-132">Per altre informazioni ed esempi, seguire i collegamenti alla pagina di riferimento per ogni metodo o proprietà.</span><span class="sxs-lookup"><span data-stu-id="64d16-132">For more information and examples, follow the links to the reference page for each method or property.</span></span>  
  
|<span data-ttu-id="64d16-133">Per</span><span class="sxs-lookup"><span data-stu-id="64d16-133">To</span></span>|<span data-ttu-id="64d16-134">Utilizza</span><span class="sxs-lookup"><span data-stu-id="64d16-134">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="64d16-135">Aggiungere uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-135">Add a namespace</span></span>|<span data-ttu-id="64d16-136">Metodo <xref:System.Xml.XmlNamespaceManager.AddNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-136"><xref:System.Xml.XmlNamespaceManager.AddNamespace%2A> method</span></span>|  
|<span data-ttu-id="64d16-137">Rimuovere uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-137">Remove a namespace</span></span>|<span data-ttu-id="64d16-138">Metodo <xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-138"><xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A> method</span></span>|  
|<span data-ttu-id="64d16-139">Trovare l'URI per lo spazio dei nomi predefinito</span><span class="sxs-lookup"><span data-stu-id="64d16-139">Find the URI for the default namespace</span></span>|<span data-ttu-id="64d16-140">Proprietà<xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-140"><xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> property</span></span>|  
|<span data-ttu-id="64d16-141">Trovare l'URI per un prefisso dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-141">Find the URI for a namespace prefix</span></span>|<span data-ttu-id="64d16-142">Metodo <xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-142"><xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A> method</span></span>|  
|<span data-ttu-id="64d16-143">Trovare il prefisso per un URI dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-143">Find the prefix for a namespace URI</span></span>|<span data-ttu-id="64d16-144">Metodo <xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-144"><xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A> method</span></span>|  
|<span data-ttu-id="64d16-145">Ottenere un elenco di spazi dei nomi nel nodo corrente</span><span class="sxs-lookup"><span data-stu-id="64d16-145">Get a list of namespaces in the current node</span></span>|<span data-ttu-id="64d16-146">Metodo <xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-146"><xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A> method</span></span>|  
|<span data-ttu-id="64d16-147">Creare l'ambito di uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="64d16-147">Scope a namespace</span></span>|<span data-ttu-id="64d16-148">Metodi <xref:System.Xml.XmlNamespaceManager.PushScope%2A> e <xref:System.Xml.XmlNamespaceManager.PopScope%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-148"><xref:System.Xml.XmlNamespaceManager.PushScope%2A> and <xref:System.Xml.XmlNamespaceManager.PopScope%2A> methods</span></span>|  
|<span data-ttu-id="64d16-149">Verificare se un prefisso è definito nell'ambito corrente</span><span class="sxs-lookup"><span data-stu-id="64d16-149">Check whether a prefix is defined in the current scope</span></span>|<span data-ttu-id="64d16-150">Metodo <xref:System.Xml.XmlNamespaceManager.HasNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-150"><xref:System.Xml.XmlNamespaceManager.HasNamespace%2A> method</span></span>|  
|<span data-ttu-id="64d16-151">Ottenere la tabella dei nomi usata per ricercare i prefissi e gli URI</span><span class="sxs-lookup"><span data-stu-id="64d16-151">Get the name table used to look up prefixes and URIs</span></span>|<span data-ttu-id="64d16-152">Proprietà<xref:System.Xml.XmlNamespaceManager.NameTable%2A></span><span class="sxs-lookup"><span data-stu-id="64d16-152"><xref:System.Xml.XmlNamespaceManager.NameTable%2A> property</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64d16-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64d16-153">See also</span></span>

- <xref:System.Xml.XmlNamespaceManager>
- [<span data-ttu-id="64d16-154">Documenti e dati XML</span><span class="sxs-lookup"><span data-stu-id="64d16-154">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
